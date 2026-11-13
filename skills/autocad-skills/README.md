# AutoCAD skills

Choose the skill that matches the files you have and the result you need.

| Skill | What it helps you do |
|---|---|
| [DWG Review](dwg-review/SKILL.md) | Inspect the source DWG, compare authorized edits against a baseline, and check plotted sheets. |
| [Drawing PDF Review](drawing-pdf-review/SKILL.md) | Review visible sheet content and produce findings tied to page locations. |
| [Drawing Redraw](drawing-redraw/SKILL.md) | Rebuild a drawing from DWG, vector PDF, or an image with known dimensions, and record the limits of the reconstruction. |
| [xdy AutoCAD MCP](xdy-autocad-mcp) | Work in AutoCAD through a configured MCP server and check the geometry in the saved DWG. Includes a Windows setup and test. |

Install a single skill by selecting its name.

```sh
npx skills add dirasx/xdy-skills --skill dwg-review --agent codex --global
```

Use [Course Project](../course-project/SKILL.md) to manage the full assignment. It uses the relevant drawing skills when they are available. To install the coursework, drawing review, and reconstruction skills together in Codex, run the following command.

```sh
npx skills add dirasx/xdy-skills --skill course-project dwg-review drawing-pdf-review drawing-redraw --agent codex --global
```

Course Project uses an existing AutoCAD MCP connection if it supports the operation you need. For a new connection to full AutoCAD on Windows, see the manual U-C4N setup and test. The `xdy-autocad-mcp` skill is optional. [Windows setup](xdy-autocad-mcp#windows-setup).

For visual review of a redrawn sheet, `compare_redraw.py` aligns two images using matching points and highlights differences in pixels. Check actual drawing dimensions in CAD. [Script source](https://github.com/pengxiaoan/autocad-dwg-redraw-skill/blob/main/skills/autocad-image-redraw/scripts/compare_redraw.py).

## Скиллы для AutoCAD

- [Проверка DWG](dwg-review/SKILL.md) помогает сверить свойства исходника, нужные правки и листы после печати.
- [Проверка чертежей в PDF](drawing-pdf-review/SKILL.md) выдаёт список замечаний с указанием листа, места, важности и следующего действия.
- [Восстановление чертежа](drawing-redraw/SKILL.md) помогает перенести геометрию из DWG, векторного PDF или изображения с известными размерами и указать точность результата.
- [xdy AutoCAD MCP](xdy-autocad-mcp#xdy-autocad-mcp-для-windows) помогает читать и править чертежи через подключённый MCP и перепроверять геометрию в сохранённом DWG.

Для установки одного скилла укажи его имя в первой команде выше. Вторая команда устанавливает комплект для курсовой с чертежами. Скилл `course-project` ведёт работу по заданию и использует доступные скиллы для AutoCAD по задаче. [Курсовая работа](../course-project/SKILL.md).

Для сравнения восстановленного листа с образцом можно использовать `compare_redraw.py`. Он совмещает два изображения по опорным точкам и показывает расхождения в пикселях. Размеры проверяй по геометрии в CAD. [Исходник скрипта](https://github.com/pengxiaoan/autocad-dwg-redraw-skill/blob/main/skills/autocad-image-redraw/scripts/compare_redraw.py).

## Sources and license notices

- DWG Review adapts the inspection and verification workflow from [Gridline](https://github.com/MakeItEzzz555/Gridline/blob/main/skills/autocad-dwg-workflow/SKILL.md). [MIT notice](dwg-review/LICENSE).
- Drawing PDF Review adapts the findings format from [Technical Drawing Reviewer](https://github.com/atenasmaini-ing/technical-drawing-reviewer/blob/main/SKILL.md). [MIT notice](drawing-pdf-review/LICENSE).
- Drawing Redraw uses original text and links to background reading on [AutoCAD PDF import](https://help.autodesk.com/view/ACD/2027/ENU/?guid=GUID-1202CC8A-364F-4E93-8E86-6F476CD83C72) and the [DWG and image redraw examples](https://github.com/pengxiaoan/autocad-dwg-redraw-skill).

## Справка по AutoCAD MCP

«Курсовая» использует уже подключённый MCP, если через него можно выполнить нужную операцию. Если на ПК работает File IPC, можно пользоваться им. Для самостоятельной настройки нового подключения к полному AutoCAD на Windows есть сервер U-C4N. Он подключается через COM и поддерживает чтение, правки и проверку сохранённого DWG. `xdy-autocad-mcp` можно установить отдельно для работы с этим сервером. [Сервер U-C4N](https://github.com/U-C4N/Autocad-MCP) · [Настройка и тест](xdy-autocad-mcp#xdy-autocad-mcp-для-windows).

Официальный MCP Autodesk работает с Autodesk Assistant. В обычном AutoCAD документированы чтение и анализ открытого чертежа, а инструменты записи доступны в Civil 3D. [Документация Autodesk](https://help.autodesk.com/cloudhelp/ENU/ADSKMCP-AutoCADCivil3DMcp/files/ADSKMCP_AutoCADCivil3DMcp_autodesk_autocad_civil_3d_mcp_html.html).

[AutoCAD MCP от Puran Water](https://github.com/puran-water/autocad-mcp) использует другой способ подключения к AutoCAD LT 2024+ в Windows. Его режим без AutoCAD тоже рассчитан на DXF.

[AutoCAD MCP от andagni](https://github.com/andagni/autocad-mcp) — отдельный проект на Rust. В README проекта сказано, что публичный Windows-релиз ещё не одобрен, а пакет для macOS отложен.

Для проверки и восстановления чертежей можно пользоваться доступными инструментами. Для `xdy-autocad-mcp` нужен подключённый AutoCAD MCP.
