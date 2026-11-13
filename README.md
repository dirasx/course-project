# xdy-skills

A collection of agent skills by xdy. Each skill lives in its own folder and can be installed separately.

[Browse on skills.sh](https://skills.sh/dirasx/xdy-skills) · [Read in Russian](#скиллы-xdy)

## AutoCAD skills

[Browse the AutoCAD collection](skills/autocad-skills). It covers [DWG review](skills/autocad-skills/dwg-review/SKILL.md), [PDF drawing review](skills/autocad-skills/drawing-pdf-review/SKILL.md), [drawing reconstruction](skills/autocad-skills/drawing-redraw/SKILL.md), and [live AutoCAD work through MCP](skills/autocad-skills/xdy-autocad-mcp).

## Course Project

A Codex skill for engineering students working on a course project. Turn an assignment brief, variant data, and a sample report into a plan you can pick up across sessions. Use the same plan to check calculations, assemble the report, and review drawings before submission.

[Release notes](https://github.com/dirasx/xdy-skills/releases/tag/v0.1.0) · [Course Project on skills.sh](https://skills.sh/dirasx/xdy-skills/course-project)

### What it helps you do

- **Start or resume a project.** Keep the plan, current status, and decisions in `PLAN.md`, `STATUS.md`, and `DECISIONS.md`.
- **Check assignment data.** Trace values back to the brief, the correct variant, and the methodology guide. Keep track of units and identify the gaps that need your input.
- **Keep deliverables consistent.** Use the same inputs for calculations, tables, plots, and drawings. Review the final report PDF and check plotted drawings against the working DWG.

For projects with drawings, add the AutoCAD skills for drafting through MCP, DWG review, PDF review, and reconstruction. [AutoCAD setup and skill selection](skills/autocad-skills).

The skill workflow and its [project rules template](skills/course-project/assets/AGENTS.md) are written in Russian.

### Install in Codex

```sh
npx skills add dirasx/xdy-skills --skill course-project --agent codex --global
```

You can also ask Codex:

> Use `$skill-installer` to install the skill from https://github.com/dirasx/xdy-skills/tree/main/skills/course-project. Use the Git installation method.

Open your project in Codex and include `$course-project` in your request:

> Use `$course-project`.

## Скиллы xdy

Коллекция скиллов для ИИ-агентов. Каждый скилл можно установить отдельно.

В [разделе AutoCAD](skills/autocad-skills#скиллы-для-autocad) собраны проверка DWG, проверка чертежей в PDF и восстановление чертежей по исходникам.
Для работы с открытым AutoCAD через MCP есть [xdy AutoCAD MCP](skills/autocad-skills/xdy-autocad-mcp#xdy-autocad-mcp-для-windows).

<a name="русская-версия"></a>

### Курсовая работа

Скилл Codex для студентов, которые делают инженерную курсовую. Помогает собрать план по заданию, данным варианта и образцу записки, а затем продолжать работу по этому плану в новых чатах.

- **Начало и продолжение работы.** Ведите план, текущий статус и решения в `PLAN.md`, `STATUS.md` и `DECISIONS.md`.
- **Проверка исходных данных.** Сверяйте значения с заданием, своим вариантом и методичкой. Учитывайте единицы измерения и отмечайте, где нужны уточнения.
- **Сборка и проверка.** Используйте общие исходные данные для расчётов, таблиц, графиков и чертежей. Перед сдачей проверьте итоговый PDF записки и сверьте PDF чертежей с рабочим DWG.

Для курсовых с чертежами можно добавить скиллы для работы через MCP, проверки DWG и PDF и восстановления чертежей. [Установка и выбор инструментов](skills/autocad-skills#скиллы-для-autocad).

Для установки выполните команду выше или попросите Codex:

> Используй `$skill-installer`. Установи скилл из https://github.com/dirasx/xdy-skills/tree/main/skills/course-project через Git.

Откройте папку курсовой и напишите:

> Используй `$course-project`.

[Инструкции скилла](skills/course-project/SKILL.md) · [Шаблон правил проекта](skills/course-project/assets/AGENTS.md)
