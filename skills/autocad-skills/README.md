# AutoCAD skills

Choose the skill that matches the files you have and the result you need.

| Skill | What it helps you do |
|---|---|
| [DWG Review](dwg-review/SKILL.md) | Inspect the source DWG, compare authorized edits against a baseline, and check plotted sheets. |
| [Drawing PDF Review](drawing-pdf-review/SKILL.md) | Review visible sheet content and produce findings tied to page locations. |
| [Drawing Redraw](drawing-redraw/SKILL.md) | Rebuild a drawing from DWG, vector PDF, or an image with known dimensions, and record the limits of the reconstruction. |

Install a single skill by selecting its name.

```sh
npx skills add dirasx/xdy-skills --skill dwg-review --agent codex --global
```

[Course Project](../course-project/SKILL.md) covers the wider coursework. These skills can also be used for standalone drawing tasks.

## Скиллы для AutoCAD

- [Проверка DWG](dwg-review/SKILL.md) помогает сверить свойства исходника, нужные правки и листы после печати.
- [Проверка чертежей в PDF](drawing-pdf-review/SKILL.md) выдаёт список замечаний с указанием листа, места, важности и следующего действия.
- [Восстановление чертежа](drawing-redraw/SKILL.md) помогает перенести геометрию из DWG, векторного PDF или изображения с известными размерами и указать точность результата.

Для установки укажи имя нужного скилла в команде выше. [Курсовая работа](../course-project/SKILL.md) помогает вести учебный проект целиком.

## Sources and license notices

- DWG Review adapts the inspection and verification workflow from [Gridline](https://github.com/MakeItEzzz555/Gridline/blob/main/skills/autocad-dwg-workflow/SKILL.md). [MIT notice](dwg-review/LICENSE).
- Drawing PDF Review adapts the findings format from [Technical Drawing Reviewer](https://github.com/atenasmaini-ing/technical-drawing-reviewer/blob/main/SKILL.md). [MIT notice](drawing-pdf-review/LICENSE).
- Drawing Redraw uses original text and links to background reading on [AutoCAD PDF import](https://help.autodesk.com/view/ACD/2027/ENU/?guid=GUID-1202CC8A-364F-4E93-8E86-6F476CD83C72) and the [DWG and image redraw examples](https://github.com/pengxiaoan/autocad-dwg-redraw-skill).

## Справка по AutoCAD MCP

[AutoCAD MCP Pro](https://github.com/U-C4N/Autocad-MCP) поддерживает работу с открытым AutoCAD через COM в Windows и отдельный режим работы с DXF без AutoCAD. [autocad-mcp-premium](https://github.com/U-C4N/Autocad-MCP/tree/main/.claude/skills/autocad-mcp-premium) — набор инструкций для агента, который работает с этим сервером. В документации Pro описаны режим чтения, ограничения по папкам и список разрешённых инструментов.

[AutoCAD MCP от Puran Water](https://github.com/puran-water/autocad-mcp) использует другой способ подключения к AutoCAD LT 2024+ в Windows. Его режим без AutoCAD тоже рассчитан на DXF.

[AutoCAD MCP от andagni](https://github.com/andagni/autocad-mcp) — отдельный проект на Rust. В README проекта сказано, что публичный Windows-релиз ещё не одобрен, а пакет для macOS отложен.

Это ссылки для знакомства с инструментами. Для работы с нашими скиллами подключение этих серверов не требуется.
