# Course Project · Курсовая

A Codex skill for engineering students working on a course project. Turn an assignment brief, variant data, and a sample report into a plan you can pick up across sessions. Use the same plan to check calculations, assemble the report, and review drawings before submission.

[Latest release](https://github.com/dirasx/course-project/releases/latest) · [skills.sh](https://skills.sh/dirasx/course-project/course-project) · [Русская версия](#русская-версия)

## What it helps you do

- **Start or resume a project.** Keep the plan, current status, and decisions in `PLAN.md`, `STATUS.md`, and `DECISIONS.md`.
- **Check assignment data.** Trace values back to the brief, the correct variant, and the methodology guide. Keep track of units and identify the gaps that need your input.
- **Keep deliverables consistent.** Use the same inputs for calculations, tables, plots, and drawings. Review the final report PDF and check plotted drawings against the working DWG.

The skill workflow and its [project rules template](skills/course-project/assets/AGENTS.md) are written in Russian.

## Install in Codex

```sh
npx skills add dirasx/course-project --skill course-project --agent codex --global
```

You can also ask Codex:

> Use `$skill-installer` to install `course-project` from https://github.com/dirasx/course-project. The skill path is `skills/course-project`. Use the Git installation method.

Open your project in Codex and include `$course-project` in your request:

> Use `$course-project`.

## Русская версия

Скилл Codex для студентов, которые делают инженерную курсовую. Помогает собрать план по заданию, данным варианта и образцу записки, а затем продолжать работу по этому плану в новых чатах.

- **Начало и продолжение работы.** Ведите план, текущий статус и решения в `PLAN.md`, `STATUS.md` и `DECISIONS.md`.
- **Проверка исходных данных.** Сверяйте значения с заданием, своим вариантом и методичкой. Учитывайте единицы измерения и отмечайте, где нужны уточнения.
- **Сборка и проверка.** Используйте общие исходные данные для расчётов, таблиц, графиков и чертежей. Перед сдачей проверьте итоговый PDF записки и сверьте PDF чертежей с рабочим DWG.

Для установки выполните команду выше или попросите Codex:

> Используй `$skill-installer`. Установи `course-project` из https://github.com/dirasx/course-project. Путь в репозитории — `skills/course-project`, метод установки — Git.

Откройте папку курсовой и напишите:

> Используй `$course-project`.

[Инструкции скилла](skills/course-project/SKILL.md) · [Шаблон правил проекта](skills/course-project/assets/AGENTS.md)
