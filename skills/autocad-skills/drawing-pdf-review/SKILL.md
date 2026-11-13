---
name: drawing-pdf-review
description: Use when reviewing technical drawing sheets exported to PDF for readability, dimensions, and consistency, especially when the source DWG or AutoCAD is unavailable.
license: MIT
---

# Проверка чертежей в PDF

Открой предоставленный PDF средствами просмотра, которые уже доступны. Сверь число листов и проверь каждый нужный лист. При необходимости увеличь фрагмент. Извлечённый текст помогает найти подпись, а её читаемость подтверждай визуально.

- **Оформление.** Проверь номера листов, штамп и редакцию, подписи, единицы, заявленный масштаб, обрезку и разборчивость линий и текста.
- **Согласованность.** Сверь обозначения, проставленные размеры, выноски и ссылки на разрезы и детали между видами и листами. При наличии задания сверь ключевые обозначения и размеры с ним. Координаты и размеры модели по пикселям не определяй.
- **Доказательства.** Привяжи каждое замечание к листу и области. Различай наблюдение и вопрос к автору. Если подпись не читается в доступном файле, так и напиши. Результат относится к предоставленному PDF. Проверку модели DWG, слоёв и связей веди отдельно при доступе к исходнику.

| Лист и место | Что видно и где это проверить | Важность | Что проверить или исправить |
|---|---|---|---|
| Лист 2, вид А | Ссылка на разрез Б есть, но среди предоставленных листов разрез не найден | Существенно | Сверить комплектность PDF и номер разреза |

Ставь существенные замечания первыми. В конце перечисли проверенные листы и ограничения просмотра.

## English

Review the supplied PDF page by page using available viewing tools. Check title blocks, labels, stated scales, visible dimensions, and cross-references. Tie each finding to a sheet and a location. Distinguish an observed issue from a question for the author, assign priority, and state the next action. List the sheets reviewed and leave model properties unverified when the DWG is unavailable.
