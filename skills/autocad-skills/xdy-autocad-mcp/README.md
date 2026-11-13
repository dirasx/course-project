# xdy AutoCAD MCP

A Codex skill for inspecting and editing drawings through AutoCAD MCP. It adapts [U-C4N's original skill](https://github.com/U-C4N/Autocad-MCP/blob/main/.claude/skills/autocad-mcp-premium/SKILL.md) and carries its [MIT notice](LICENSE). For live DWG work on Windows, use full AutoCAD and the separate [U-C4N server package](https://pypi.org/project/autocad-mcp-pro/1.8.0/).

```sh
npx skills add dirasx/xdy-skills --skill xdy-autocad-mcp --agent codex --global
```

## Windows setup and read-only test

1. On your Windows PC, create a `cad-mcp-test` folder in your user folder, with a `drawings` subfolder. With full AutoCAD, save a sample DWG in that subfolder with declared units and a circle of known diameter. Open that drawing in AutoCAD.
2. If you need the MCP server, open PowerShell in the test folder. Use Python 3.11 or newer to create an isolated environment and install the release used in this example.

   ```powershell
   py -3 -m venv .venv
   .\.venv\Scripts\python.exe -m pip install 'autocad-mcp-pro[com]==1.8.0'
   ```

3. Add the following to your [local Codex MCP configuration](https://developers.openai.com/codex/mcp). Replace the example paths with yours. Keep AutoCAD open and start a fresh local Codex session on the same PC after saving the configuration.

   ```toml
   [mcp_servers.autocad]
   command = 'C:\Users\YourName\cad-mcp-test\.venv\Scripts\autocad-mcp.exe'
   env = { AUTOCAD_MCP_BACKEND = "com", CAD_LAUNCH = "never", READ_ONLY = "true", ALLOWED_PATHS = 'C:\Users\YourName\cad-mcp-test\drawings', TOOL_DENYLIST = "system_run_command,system_run_lisp" }
   ```

4. In Codex, give the exact path to the drawing and the identity of the known circle. Use `system_status` to confirm the COM backend and read-only policy, and `entity_list` or `entity_get` to measure the circle from its geometry. This test covers connection and reads. An edit test requires explicitly enabling writes and using a disposable copy, then saving, reopening, and measuring it again.

## xdy AutoCAD MCP для Windows

Скилл для чтения, правки и проверки чертежей в Codex через подключённый AutoCAD MCP. Сервер ставится отдельно. Для первого теста понадобится полный AutoCAD на том же ПК и тестовый DWG с заданными единицами и окружностью известного диаметра. Открой DWG вручную.

Установи скилл командой в начале страницы. Если сервер ещё не подключён, создай тестовую папку с подпапкой `drawings`, положи туда DWG и выполни [настройку для Windows](#windows-setup-and-read-only-test). В конфигурации подставь свои пути. После сохранения настроек заново запусти локальный Codex и отправь ему такой запрос:

> Используй `$xdy-autocad-mcp`. Проверь подключение к открытому тестовому DWG `[полный путь]` через COM и подтверди режим только чтения. Назови точный путь файла, единицы и слой контрольной окружности. Через `entity_list` или `entity_get` прочитай геометрию окружности и определи её диаметр. Чертёж не меняй и не сохраняй.

Сверь измеренный диаметр со значением, заданным при создании чертежа. Для отдельного теста записи открой одноразовую копию DWG из тестовой папки, выставь `READ_ONLY = "false"` и перезапусти Codex. Попроси его изменить диаметр, сохранить копию, заново открыть её и считать размер из геометрии.
