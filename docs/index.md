# Отчет
## Ссылка GitHub

[https://github.com/lemmaksim44/mkdocs-site-task2](https://github.com/lemmaksim44/mkdocs-site-task2)  


### Кастомизация темы

Следуя документации [https://www.mkdocs.org/dev-guide/themes/](https://www.mkdocs.org/dev-guide/themes/), была разработана собственная тема для сайта.
Header и Footer были реализованы с использованием библиотеки Bootstrap. Для главной страницы создан отдельный дизайн, в котором в Header отображается название сайта, для остальных страниц название убрано.
Поскольку сайт использует готовую библиотеку с минифицированными файлами, минификация была добавлена только для HTML страниц с помощью плагина `minify`. На все страницы добавлены метатеги для указания описания сайта и автора.

mkdocs.yml
```yml
site_name: "Site"
site_description: "Отчет для задания 2.2"
site_author: "Лежанков Максим"

theme:
  name: null
  custom_dir: custom

nav:
  - Главная: index.md
  - Документация MkDocs: documentation.md

plugins:
  - minify:
      minify_html: true
```

```html
<meta name="description" content="{{ config.site_description | default('') }}">
<meta name="author" content="{{ config.site_author | default('') }}">
```

### Этапы сборки и деплоя

Ссылка на action.yml: [https://github.com/lemmaksim44/mkdocs-site-task2/blob/main/.github/workflows/action.yml](https://github.com/lemmaksim44/mkdocs-site-task2/blob/main/.github/workflows/action.yml)

Описание этапов:

1. Сборка сайта MkDocs
    - Преобразование Markdown файлов в HTML с использованием кастомного шаблона
    - Автоматическая генерация навигации и ссылок
    - Минификация HTML страниц

2. Валидация HTML

3. Деплой на GitHub Pages