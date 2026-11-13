# xdy AutoCAD MCP

A Codex skill for inspecting and editing drawings through AutoCAD MCP. It adapts [U-C4N's original skill](https://github.com/U-C4N/Autocad-MCP/blob/main/.claude/skills/autocad-mcp-premium/SKILL.md) and carries its [MIT notice](LICENSE). For live DWG work on Windows, use full AutoCAD and the separate [U-C4N server package](https://pypi.org/project/autocad-mcp-pro/1.8.0/).

The optional skill can be installed separately from the server and its test.

```sh
npx skills add dirasx/xdy-skills --skill xdy-autocad-mcp --agent codex --global
```

## Windows setup

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
   env = { AUTOCAD_MCP_BACKEND = "com", CAD_LAUNCH = "never", READ_ONLY = "false", ALLOWED_PATHS = 'C:\Users\YourName\cad-mcp-test\drawings', TOOL_DENYLIST = "system_run_command,system_run_lisp" }
   ```

4. In Codex, give the exact path to the drawing and the identity of the known circle. Use `system_status` to confirm the COM backend and write access. Open a disposable test DWG through `drawing_open`, edit it, save and reopen it, and measure its geometry. Add the actual project folder to `ALLOWED_PATHS` and restart the local Codex session after changing the configuration.

A profile with `READ_ONLY = "true"` can inspect an already open DWG. U-C4N's `drawing_open` changes the active session and requires a profile that allows mutations. For MCP to open drawings itself, use a dedicated working folder in `ALLOWED_PATHS`, set `READ_ONLY = "false"` in that profile, and restart the local Codex session. Check the tool through `search_tools`. Keep AutoCAD running if `CAD_LAUNCH = "never"`.

## xdy AutoCAD MCP для Windows

Скилл для чтения, правки и проверки чертежей в Codex через подключённый AutoCAD MCP. Сервер ставится отдельно. Для первого теста понадобится полный AutoCAD на том же ПК и тестовая копия DWG.

Если сервер ещё не подключён, создай тестовую папку с подпапкой `drawings`, положи туда DWG и выполни настройку для Windows. В конфигурации подставь свои пути. После сохранения настроек заново запусти локальный Codex. Скилл можно установить отдельно командой в начале страницы. [Настройка для Windows](#windows-setup).

Попроси Codex настроить сервер в том же чате:

> Проверь подключённый AutoCAD MCP и настрой U-C4N для папки моей курсовой. Если сервер уже есть, используй его. Включи открытие и редактирование DWG через COM, сохрани остальные настройки и проверь создание и правку объекта на отдельной тестовой копии.

После изменения конфигурации перезапусти локальную сессию Codex и продолжи проверку. Для работы с другими папками добавь их в `ALLOWED_PATHS`. Режим `READ_ONLY = "true"` предназначен для чтения уже открытого чертежа.
