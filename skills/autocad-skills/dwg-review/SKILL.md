---
name: dwg-review
description: Use when inspecting an AutoCAD DWG before editing or issuing it, checking DWG changes against a baseline, or comparing layouts and plotted PDFs with the source drawing.
license: MIT
---

# Проверка DWG

Начни с проверки чертежа без изменений. Сначала проверь инструменты подключённого AutoCAD MCP, включая поиск на сервере, если он есть. Сверь полный путь и нужный лист. Если режим чтения не даёт открыть DWG через MCP, попроси пользователя открыть его и продолжи проверки через MCP. Если подключение недоступно, сообщи об этом. Используй другой инструмент чтения DWG или Computer Use, если запрос допускает этот способ. При наличии только PDF проверь видимое и укажи, какие проверки требуют исходного DWG.

1. **Исходное состояние.** Зафиксируй путь и версию файла, единицы, начало координат, рабочую систему координат и границы модели, если они важны. Проверь нужные слои и блоки, внешние ссылки, шрифты и типы линий. Отметь отсутствующие зависимости.
2. **Если запрос включает правку.** Работай на копии. Перед пакетным изменением уточни, какие объекты должны попасть под него, и проверь выборку на малом примере. Сравни состояние до и после, используя идентификаторы, свойства или количество объектов там, где это помогает увидеть лишние изменения. После сохранения открой копию заново и сверяй её с исходником по неизменяемым свойствам, важным для задачи.
   Для сравнения двух сохранённых версий укажи полные пути и версии файлов. Сопоставь единицы, пространства и листы, затем сравни важные для задачи геометрию, размеры, подписи, блоки, слои и внешние ссылки. Используй доступное сравнение DWG, если оно подходит к этим файлам, либо считай свойства объектов обеих версий. Идентификаторы объектов могут измениться при пересохранении, поэтому проверяй соответствие по типу, положению и свойствам и отмечай неоднозначные совпадения. Раздели ожидаемые изменения, неожиданные отличия и непроверенные элементы. Для контрольных размеров приведи источник, ожидаемое и измеренное значения, единицы и отклонение. Зафиксируй, какие объекты и листы удалось сравнить.
3. **Листы и печать.** Сверь форматы листов, масштабы видовых экранов и настройки печати. В готовом PDF проверь рамку, штамп, размеры, обрезку, толщину линий, штриховку и читаемость подписей. Сопоставь каждый проверенный лист с его представлением в DWG.
4. **Результат.** Укажи файл или лист, что наблюдал, откуда это известно и что осталось непроверенным. Если удалось открыть только PDF, не подтверждай по нему слои, разрешение внешних ссылок и точную геометрию модели.

## English

Start with read-only inspection. Check the configured AutoCAD MCP first and use its tool search when available. Confirm the drawing identity and record relevant units, coordinates, layers, blocks, external references, fonts, layouts, and plot settings. Report unavailable MCP access before using a different tool that fits the request. When edits are requested, work on a copy, preview the intended edits, then reopen the saved file and compare it with the baseline. Identify both files and compare the relevant geometry, dimensions, annotations, blocks, layers and references. Match objects by type, location and properties when handles change, and report ambiguous matches, expected changes, unexpected differences and coverage. Check plotted sheets for scale, clipping, legibility, and lineweights. With PDF alone, review visible sheets and leave native DWG checks open.
