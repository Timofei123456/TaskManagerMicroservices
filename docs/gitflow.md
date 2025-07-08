# Gitflow для микросервисного проекта

## Основные ветки

- `main` — стабильная, релизная версия проекта
- `develop` — основная ветка для разработки
- `feature/xxx` — ветки для новых фич/задач
- `bugfix/xxx` — ветки для исправления багов
- `hotfix/xxx` — срочные фиксы для main

## Как работать

1. Всегда работай в отдельных ветках! Не коммить в main/develop напрямую.
2. Для новой задачи — создай ветку от develop:
   ```
   git checkout develop
   git pull
   git checkout -b feature/my-feature
   ```
3. Закончил — делай осмысленный коммит:
   ```
   git add .
   git commit -m "Добавил авторизацию через OAuth2 в user-service"
   ```
4. Запушь ветку:
   ```
   git push origin feature/my-feature
   ```
5. Создай Pull Request в develop, после ревью — замёржь.
6. После завершения задачи — удали feature-ветку:
   ```
   git branch -d feature/my-feature
   git push origin --delete feature/my-feature
   ```

## Релизы

- Перед релизом мержишь develop в main через Pull Request.
- Обязательно проверяй тесты и CI!

Подробнее смотри [Gitflow cheatsheet](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow)