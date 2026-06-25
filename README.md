# Veai media — arXiv-дайджест «Риски и качество ИИ-кода» (09–16 июня 2026)

Самодостаточный статический сайт (можно открыть `2026-06-16-arxiv-ai-code-quality-weekly.html`
напрямую в браузере). Все пути внутри — относительные, внешних зависимостей нет.

## Что внутри

| Путь | Назначение |
|------|-----------|
| `2026-06-16-arxiv-ai-code-quality-weekly.html` | Главная страница дайджеста (вход) |
| `assets/veai-logo.svg` | Логотип Veai (шапка + футер всех страниц) |
| `arxiv/*.html` | 16 страниц-переводов статей, на которые ссылается главная |
| `arxiv/article.css` | Общие стили для всех страниц переводов |
| `arxiv/assets/<id>/...` | Иллюстрации (figures) к конкретным переводам |
| `webinar-code-quality-ai/images/*.svg` | 2 SVG, встроенные в перевод `arxiv/2606.14796.html` |
| `articles/habr/cursor-vs-veai-for-developers/images/*` | 2 картинки, встроенные в перевод `arxiv/2606.14796.html` |

## Карта зависимостей

- Главная → `assets/veai-logo.svg`, 16 × `arxiv/2606.*.html`
- Каждая `arxiv/2606.*.html` → `arxiv/article.css`, `../assets/veai-logo.svg`
- Страницы с иллюстрациями → `arxiv/assets/<id>/...`
- `arxiv/2606.14796.html` дополнительно → `../webinar-code-quality-ai/images/`
  и `../articles/habr/cursor-vs-veai-for-developers/images/`

## Служебные файлы (не часть сайта, можно не переносить)

- `arxiv/explyt-removal-report.md`, `arxiv/translation-style-reference.md` — рабочие заметки
- `arxiv/2606.12620.html`, `arxiv/2606.13918.html`,
  `arxiv/2606.12986-full-translation.html`, `arxiv/2606.15834.reference.html`
  — версии переводов, на которые главная страница НЕ ссылается

## Как встроить в veai-docs (Docusaurus)

Это готовый статический HTML, а не MDX. Самый простой путь — положить целиком в
`static/` целевого проекта, тогда сайт будет доступен по прямому URL без сборки:

```
veai-docs/static/arxiv-digest-2026-06-16/   ← содержимое этого бандла
```

Открывается как `/<baseUrl>/arxiv-digest-2026-06-16/2026-06-16-arxiv-ai-code-quality-weekly.html`.
Относительные пути сохранятся рабочими. При необходимости переименуйте корневой HTML в `index.html`.
