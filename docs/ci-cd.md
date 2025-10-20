# CI/CD в проекте

Реализовано с помощью GitHub Actions.  

## Ручные апрувы PR

Для выполнения требований ДЗ на +1 балл, апрувы делаются не с помощью встроенного инструмента GitHub.

Они делаются с помощью джобы [manual-approval.yml](https://github.com/Xausdorf/grudina-hw3/blob/main/.github/workflows/manual-approval.yml).
Она создает issue в котором как минимум 3 человека из команды должны написать комментарий `approve` чтобы апрувнуть. 
При этом эта джоба является status check'ом в PR, поэтому нельзя будет замерджить до апрува.

![Пример ручного апрува](https://github.com/Xausdorf/grudina-hw3/blob/main/assets/approve_example.png)

## Автоформатирование кода

При изменении Markdown файлов вызывается джоба [format-md.yml](https://github.com/Xausdorf/grudina-hw3/blob/main/.github/workflows/format-md.yml) которая автоматически форматирует код и добавляет изменения в PR.

## Деплой в GitHub Pages

При пуше изменений в `main` вызывается джоба [deploy-to-gh-pages.yml](https://github.com/Xausdorf/grudina-hw3/blob/main/.github/workflows/deploy-to-gh-pages.yml) которая автоматически генерирует сайт для GitHub Pages в ветку `gh-pages` откуда сайт деплоится в GitHub Pages.