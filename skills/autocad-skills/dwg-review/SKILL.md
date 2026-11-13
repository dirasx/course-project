---
name: dwg-review
description: Use when inspecting an AutoCAD DWG before editing or issuing it, checking DWG changes against a baseline, or comparing layouts and plotted PDFs with the source drawing.
license: MIT
---

# Проверка DWG

Начни с проверки чертежа без изменений. Сначала проверь инструменты подключённого AutoCAD MCP, включая поиск на сервере, если он есть. Сверь полный путь и нужный лист. Если режим чтения не даёт открыть DWG через MCP, попроси пользователя открыть его и продолжи проверки через MCP. Если подключение недоступно, сообщи об этом. Используй другой инструмент чтения DWG или Computer Use, если запрос допускает этот способ. При наличии только PDF проверь видимое и укажи, какие проверки требуют исходного DWG.

1. **Исходное состояние.** Зафиксируй путь и версию файла, единицы, начало координат, рабочую систему координат и границы модели, если они важны. Проверь нужные слои и блоки, внешние ссылки, шрифты и типы линий. Отметь отсутствующие зависимости.
2. **Если запрос включает правку.** Работай на копии. Перед пакетным изменением уточни, какие объекты должны попасть под него, и проверь выборку на малом примере. Сравни состояние до и после, используя идентификаторы, свойства или количество объектов там, где это помогает увидеть лишние изменения. После сохранения открой копию заново и сверяй её с исходником по неизменяемым свойствам, важным для задачи.
3. **Листы и печать.** Сверь форматы листов, масштабы видовых экранов и настройки печати. В готовом PDF проверь рамку, штамп, размеры, обрезку, толщину линий, штриховку и читаемость подписей. Сопоставь каждый проверенный лист с его представлением в DWG.
4. **Результат.** Укажи файл или лист, что наблюдал, откуда это известно и что осталось непроверенным. Если удалось открыть только PDF, не подтверждай по нему слои, разрешение внешних ссылок и точную геометрию модели.

## English

Start with read-only inspection. Check the configured AutoCAD MCP first and use its tool search when available. Confirm the drawing identity and record relevant units, coordinates, layers, blocks, external references, fonts, layouts, and plot settings. Report unavailable MCP access before using a different tool that fits the request. When edits are requested, work on a copy, preview the intended edits, then reopen the saved file and compare the result with the baseline. Check plotted sheets for scale, clipping, legibility, and lineweights. Report evidence and unverified properties separately. With PDF alone, review visible sheets and leave native DWG checks open.
