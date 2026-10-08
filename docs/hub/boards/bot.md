# Доска BOT — Штаб инженера бота

<!-- Шаблон из набора https://github.com/RickOBrian/aid/tree/main/docs/hub/kit.
     Публичный репозиторий — только роли, никаких имён и контактов. -->

Активные задачи по чатам. Ведёт «AID · Hub · Штаб» инженера бота
(`../ORCHESTRATION.md` §9, ADR-041). Задачи — `AID-BOT-<n>`. Строка
закрывается ссылкой на PR или решение.

Решения в этом Штабе принимает **инженер бота** — только по своему
продукту (Bot · Request). Чужие продукты — issue владельцу (`hub`,
`to:<продукт>`), системный уровень — плюс `decision:pd`.

Статусы: `в работе` · `ждёт инженера` · `ждёт PD` · `ждёт <чат>` · `блокер` · `сверить` · `отложено`

## Чаты

| Чат | Папка | Что правит | Вход в контекст |
|---|---|---|---|
| AID · Hub · Штаб | `~/Projects/aid-hub` | `docs/hub/boards/bot.md` | `docs/hub/ORCHESTRATION.md` → эта доска |
| AID · Bot · Request | `~/Projects/aid-bot-request`, клон репозитория бота | весь репозиторий бота | его `CLAUDE.md` → `BOT-OVERVIEW.md` |

Код бота — во внешнем приватном репозитории `effects121-lang/ds-request-bot`.
Контракт бота с продуктами AID — `tools/aid-bot/` в этом репозитории, ведёт
PD; правки в нём — через PR PD, инженер бота — ревьюер.

## Источники для `/plan`

Кроме источников из `.claude/skills/plan/SKILL.md` (с поправкой: доска —
этот файл, решения — «Решения инженера» ниже, вопросы — к инженеру бота):

- issues в `RickOBrian/aid` с меткой `to:bot-request`, а также issues с
  `hub`, где в тексте упомянут бот, пока метку не поставили;
- открытые вопросы контракта: `tools/aid-bot/OPEN-QUESTIONS.md` на
  `origin/main`;
- PR и CI бота: `gh pr list --repo effects121-lang/ds-request-bot --state open`.

## Активные

| ID | Чат | Задача | Статус |
|---|---|---|---|
| AID-BOT-4 | Bot | Опрос бэкенда предложений LU и уведомления в Telegram — по решению в [#98](https://github.com/RickOBrian/aid/issues/98#issuecomment-6016709105) | ждёт Штаб LU (endpoint, схема, ключ) |
| AID-BOT-5 | Bot | AID-12 Штаба PD — уведомления в Telegram о задачах между Штабами (ADR-042, `../ORCHESTRATION.md` §9): опрос GitHub вместо webhook ([#136](https://github.com/RickOBrian/aid/issues/136)), контракт уведомлений [#137](https://github.com/RickOBrian/aid/pull/137) v0.2.0, срок 15.10 | ждёт инженера: Approve #137, затем реализация |
| AID-BOT-6 | Bot | AID-6 Штаба PD — пилот «плагин в боте всегда актуальный»: контракт `tools/aid-bot/contracts/plugin-release.md` ([#71](https://github.com/RickOBrian/aid/pull/71)) смержен 2026-10-08 | в работе — реализация в боте |

## Вопросы инженера

Списки, собранные скиллом `/plan`: `PLAN-<дата>`, пункты с приоритетом
P0–P3, источник. Пункт закрывается ссылкой на строку в «Решениях».

_Пока списков нет._

## Решения инженера

Формулировка — дословно. Запись на `main` — разрешение начать работу.

| Дата | Задача | Кому | Решение (дословно) |
|---|---|---|---|
| 2026-10-06 | AID-BOT-3 | Штаб LU, [#98](https://github.com/RickOBrian/aid/issues/98#issuecomment-6016709105) | «Бэкенд у LU, бот опрашивает» |

## Закрыто

| ID | Чат | Что | Итог |
|---|---|---|---|
| AID-BOT-3 | Bot | Ответ Штабу LU по этапу 7 плагина | решение в [#98](https://github.com/RickOBrian/aid/issues/98#issuecomment-6016709105) |
| AID-BOT-1 | Все | Переход на оркестрацию: имена, группа, работа из своей папки | 2026-10-06: папка сменена (`BOARD.md`, AID-1 · Bot) |
| AID-BOT-2 | Hub | Путь к доске в `owners.json` → `board` ([#99](https://github.com/RickOBrian/aid/issues/99)) | 2026-10-08: [#100](https://github.com/RickOBrian/aid/pull/100) смержен, путь вписан в `owners.json` |
