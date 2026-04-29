# Impeccable Korn

Личная адаптация проекта **Impeccable** для работы с AI-агентами, в первую очередь с **Codex CLI** через механизм **Agent Skills**.

Impeccable помогает AI-агенту проектировать, проверять и улучшать frontend-интерфейсы не по шаблону, а с опорой на дизайн-систему, UX-логику, типографику, цвет, адаптивность, состояния интерфейса и список запрещённых AI-антипаттернов.

> Важно: этот репозиторий основан на оригинальном проекте [Paul Bakaus / Impeccable](https://github.com/pbakaus/impeccable). Лицензия Apache 2.0 сохранена. Эта версия используется как личная рабочая адаптация под мои проекты и дальнейшие доработки.

## Зачем нужен Impeccable

Большинство LLM-моделей обучались на похожих frontend-примерах. Поэтому без дополнительных правил они часто создают одинаковые интерфейсы:

- шрифт Inter или системный sans-serif по умолчанию;
- фиолетовые и синие градиенты;
- карточки внутри карточек;
- серый текст на цветном фоне;
- одинаковые сетки с иконкой, заголовком и текстом;
- тёмный SaaS-интерфейс без реальной причины;
- декоративные эффекты, которые выглядят как типичный AI-output.

Impeccable снижает этот риск за счёт:

- одного расширенного skill `impeccable`;
- 23 команд для аудита, полировки, адаптации, типографики, анимации, UX-copy и других задач;
- reference-файлов по ключевым направлениям frontend-дизайна;
- CLI-детектора UI-антипаттернов;
- поддержки нескольких AI-харнесов: Codex, Cursor, Claude Code, Gemini CLI, GitHub Copilot и других.

## Главный сценарий этого форка

Эта версия в первую очередь предназначена для личного использования в **Codex CLI**.

Правильный путь для Codex:

```text
.agents/skills/impeccable/
```

Не основной путь для Codex:

```text
.codex/skills/
```

Папка `.codex` может присутствовать как legacy-выход сборки, но для обычной работы с Codex следует использовать именно `.agents`.

## Что входит в проект

### Skill `impeccable`

Основной skill расположен здесь:

```text
source/skills/impeccable/SKILL.md
```

Он используется, когда нужно:

- спроектировать интерфейс;
- сделать редизайн;
- провести UX/UI-аудит;
- улучшить визуальную иерархию;
- проверить accessibility;
- усилить адаптивность;
- улучшить UX-copy;
- убрать AI-шаблонность;
- подготовить интерфейс к production;
- выстроить дизайн-систему.

### Reference-файлы

Внутри skill есть справочные материалы:

| Файл | Что покрывает |
|---|---|
| `typography.md` | Типографика, иерархия, font pairing, размеры, OpenType |
| `color-and-contrast.md` | Цвет, OKLCH, контраст, тёмная тема, accessibility |
| `spatial-design.md` | Отступы, сетки, визуальный ритм, композиция |
| `motion-design.md` | Анимации, easing, stagger, reduced motion |
| `interaction-design.md` | Формы, focus states, loading states, взаимодействие |
| `responsive-design.md` | Mobile-first, fluid layout, container queries |
| `ux-writing.md` | Кнопки, ошибки, пустые состояния, микротексты |

## Команды Impeccable

Все команды логически доступны через `impeccable`.

| Команда | Назначение |
|---|---|
| `impeccable craft` | Полный цикл: сначала UX/UI-форма задачи, потом реализация |
| `impeccable teach` | Первичная настройка контекста проекта, создание `PRODUCT.md` и `DESIGN.md` |
| `impeccable document` | Генерация `DESIGN.md` на основе существующего кода |
| `impeccable extract` | Извлечение повторяемых компонентов и токенов в дизайн-систему |
| `impeccable shape` | Планирование UX/UI до написания кода |
| `impeccable critique` | UX-критика: иерархия, ясность, эмоциональный эффект |
| `impeccable audit` | Технический аудит: accessibility, performance, responsive, anti-patterns |
| `impeccable polish` | Финальная полировка перед релизом |
| `impeccable bolder` | Сделать скучный дизайн смелее и выразительнее |
| `impeccable quieter` | Успокоить слишком агрессивный или перегруженный дизайн |
| `impeccable distill` | Упростить интерфейс до сути |
| `impeccable harden` | Production-ready: ошибки, i18n, переполнение текста, edge cases |
| `impeccable onboard` | Онбординг, first-run flow, пустые состояния |
| `impeccable animate` | Осмысленная анимация и micro-interactions |
| `impeccable colorize` | Стратегическое добавление цвета |
| `impeccable typeset` | Исправление типографики |
| `impeccable layout` | Исправление layout, spacing и визуального ритма |
| `impeccable delight` | Добавление деталей, которые делают интерфейс приятнее |
| `impeccable overdrive` | Более сложные и эффектные визуальные решения |
| `impeccable clarify` | Улучшение UX-copy, label-ов и сообщений об ошибках |
| `impeccable adapt` | Адаптация под устройства и экраны |
| `impeccable optimize` | Оптимизация UI-производительности |
| `impeccable live` | Визуальная итерация элементов в браузере |

## Использование в Codex

В Codex надёжнее обращаться к skill явно, а не рассчитывать на slash-команды.

Примеры рабочих запросов:

```text
Используй skill impeccable. Проведи audit текущего интерфейса.
```

```text
Используй skill impeccable. Сделай polish экрана карточки клиента, не меняя бизнес-логику.
```

```text
Используй skill impeccable. Проверь Telegram Mini App на визуальную иерархию, адаптивность, UX-copy и AI-шаблонность.
```

```text
Используй skill impeccable. Улучши CRM-интерфейс: отступы, карточки, состояния загрузки, ошибки, empty states, mobile.
```

```text
Используй skill impeccable. Проверь интерфейс на типичные AI-антипаттерны и предложи план исправлений перед изменением кода.
```

## Установка для Codex

### 1. Собрать проект

```bash
bun install
bun run build
```

### 2. Установить skill локально в конкретный проект

```bash
cp -r dist/agents/.agents /path/to/your-project/
```

После этого структура проекта должна быть такой:

```text
your-project/
└─ .agents/
   └─ skills/
      └─ impeccable/
         ├─ SKILL.md
         ├─ reference/
         ├─ scripts/
         └─ agents/
            └─ openai.yaml
```

### 3. Установить skill глобально для пользователя

```bash
mkdir -p ~/.agents/skills
cp -r dist/agents/.agents/skills/* ~/.agents/skills/
```

Локальная установка удобнее для тестов на одном проекте. Глобальная установка удобнее, если skill нужен во всех проектах.

## Рекомендуемый личный workflow

### Шаг 1. Подготовить проект

В проекте, где будет использоваться skill, желательно иметь:

```text
PRODUCT.md
DESIGN.md
```

`PRODUCT.md` отвечает за продуктовый контекст:

- кто пользователь;
- какая задача продукта;
- какой тон коммуникации;
- какие ограничения;
- какой визуальный и эмоциональный эффект нужен.

`DESIGN.md` отвечает за визуальную систему:

- цвета;
- типографику;
- компоненты;
- spacing;
- radii;
- состояния;
- правила адаптивности.

### Шаг 2. Попросить Codex провести аудит

```text
Используй skill impeccable. Проведи audit проекта. Сначала дай список проблем по приоритету P0, P1, P2, затем предложи план исправлений. Код пока не меняй.
```

### Шаг 3. После плана разрешить изменения

```text
Теперь внеси исправления из P0 и P1. Не меняй бизнес-логику, API, структуру данных и названия существующих переменных без необходимости.
```

### Шаг 4. Финальная полировка

```text
Используй skill impeccable. Сделай polish изменённых экранов: проверь отступы, типографику, mobile, empty states, loading states и ошибки.
```

## CLI-детектор антипаттернов

Проект содержит отдельный CLI для поиска UI-антипаттернов без AI-харнеса.

```bash
npx impeccable detect src/
npx impeccable detect index.html
npx impeccable detect https://example.com
npx impeccable detect --fast --json .
```

Детектор ищет проблемы двух типов:

1. **AI slop**: признаки шаблонного AI-интерфейса.
2. **Design quality**: реальные проблемы качества интерфейса.

Примеры проверок:

- side-tab borders;
- purple gradients;
- gradient text;
- dark glow;
- nested cards;
- overused fonts;
- low contrast;
- cramped padding;
- skipped headings;
- tiny text;
- layout property animation.

## Важные ограничения текущей версии

### 1. Это личный форк, а не полностью переименованный продукт

Внутри проекта часть metadata, package-информации, install/update-логики и внешних ссылок всё ещё может указывать на оригинальный Impeccable.

Для личного использования это не критично.

Для публичного продукта нужно отдельно:

- переименовать package;
- заменить repository URL;
- заменить install/update upstream;
- убрать зависимость от `impeccable.style`;
- обновить npm/package metadata;
- проверить license/notice attribution.

### 2. Для Codex использовать `.agents`, а не `.codex`

`.codex` может присутствовать как legacy-формат. Основной рабочий путь для Codex:

```text
.agents/skills/
```

### 3. Осторожно с pin-командами

Команда `pin` может быть удобной для создания коротких shortcut-команд, но для Codex на текущем этапе безопаснее не использовать её как основной механизм.

Лучше обращаться к skill явно:

```text
Используй skill impeccable. Выполни audit.
```

## План личной доработки Korn-версии

### Этап 1. Стабилизировать Codex-сценарий

- Проверить сборку `bun run build`.
- Проверить наличие `dist/agents/.agents/skills/impeccable`.
- Установить skill в тестовый проект.
- Убедиться, что Codex видит skill.
- Проверить команды `audit`, `polish`, `harden`, `clarify` на реальном интерфейсе.

### Этап 2. Добавить личный бизнес-контекст

Планируемые reference-файлы:

```text
source/skills/impeccable/reference/korn-context.md
source/skills/impeccable/reference/premium-real-estate.md
source/skills/impeccable/reference/telegram-mini-app.md
source/skills/impeccable/reference/ai-crm.md
source/skills/impeccable/reference/russian-ux-copy.md
source/skills/impeccable/reference/sales-psychology-ui.md
```

Их задача: адаптировать Impeccable под реальные проекты:

- премиальная недвижимость;
- AI CRM для риелторов;
- Telegram Mini App;
- WebApp-интерфейсы;
- доверие, безопасность, статус;
- русскоязычный UX-copy;
- психология клиента и продаж.

### Этап 3. Усилить тесты под Codex

Желательно добавить тесты, которые проверяют:

- генерацию `.agents/skills/impeccable/SKILL.md`;
- наличие `agents/openai.yaml`;
- отсутствие незаменённых placeholders;
- копирование `reference/` и `scripts/`;
- корректность Codex-инструкций.

### Этап 4. Только потом думать о публичной версии

Публичная версия имеет смысл только после того, как личная версия стабильно работает в реальных проектах.

## Поддерживаемые инструменты

Проект умеет собирать skill под разные AI-харнесы:

- Codex CLI;
- Cursor;
- Claude Code;
- Gemini CLI;
- GitHub Copilot;
- OpenCode;
- Kiro;
- Pi;
- Qoder;
- Trae;
- Rovo Dev.

Для моего рабочего сценария основной инструмент: **Codex CLI**.

## Структура проекта

```text
source/                          исходники skill
  skills/impeccable/
    SKILL.md                      главный skill
    reference/                    справочные материалы
    scripts/                      служебные скрипты skill

scripts/                         сборка и трансформация
  build.js                        основной build pipeline
  lib/transformers/               provider-конфиги и фабрика

src/                             runtime-код CLI-детектора
  detect-antipatterns.mjs         основной anti-pattern detector

bin/                             CLI-вход
  cli.js
  commands/skills.mjs

tests/                           тесты
public/                          сайт и демо-страницы
server/                          локальный dev/API server
dist/                            сгенерированные выходы под разные инструменты
build/                           сборка сайта
```

## Разработка

Установка зависимостей:

```bash
bun install
```

Сборка:

```bash
bun run build
```

Полная пересборка:

```bash
bun run rebuild
```

Тесты:

```bash
bun run test
```

Локальный dev-сервер:

```bash
bun run dev
```

## Что не стоит делать без необходимости

- Не редактировать вручную файлы в `dist/`, если изменение должно жить постоянно.
- Не начинать с полного переименования всего проекта, если цель только личное использование.
- Не использовать `.codex` как основной путь для Codex.
- Не делать публичный npm-пакет до очистки metadata и install/update-логики.
- Не менять `src/detect-antipatterns.mjs` без тестов, потому что он используется CLI, browser-версией, extension и сайтом.

## Лицензия и атрибуция

Лицензия: Apache 2.0. См. [LICENSE](LICENSE).

Проект основан на оригинальном Impeccable от Paul Bakaus и использует идеи Anthropic `frontend-design` skill. См. [NOTICE.md](NOTICE.md) для атрибуции.

Оригинальный проект:

- GitHub: https://github.com/pbakaus/impeccable
- Сайт: https://impeccable.style

Эта версия:

- GitHub: https://github.com/KornArs/impeccable_korn
- Основной сценарий: личное использование и доработка под Codex CLI.
