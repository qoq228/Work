# Таблица замены термина "канал" на "аккаунт"

В рамках унификации терминологии ниже представлена таблица с расхождениями, требующими замены во всех документах.

## 1. Реализация NEW

| Раздел | Текущий термин | Предлагаемая замена |
|--------|---------------|-------------------|
| Публичный API модуля коммуникаций - Основные группы эндпоинтов | **1. Управление каналами** | **1. Управление аккаунтами** |
| Публичный API - Управление каналами | **POST /channels** - Подключение нового канала | **POST /accounts** - Подключение нового аккаунта |
| Публичный API - Управление каналами | **DELETE /channels/{channelId}** - Отключение канала | **DELETE /accounts/{accountId}** - Отключение аккаунта |
| Публичный API - Управление каналами | При получении запроса на подключение канала от провайдера... | При получении запроса на подключение аккаунта от провайдера... |
| Публичный API - Управление каналами | При получении запроса на отключение канала от провайдера... | При получении запроса на отключение аккаунта от провайдера... |
| Структура конфигурации провайдера - Обязательные эндпоинты | `getChannels` - Запрос списка каналов | `getAccounts` - Запрос списка аккаунтов |
| Активация и деактивация токена, пункт 4 | Реализовать иконку-заглушку для каналов код которых не поддерживается... | Реализовать иконку-заглушку для аккаунтов, код которых не поддерживается... |
| Активация и деактивация токена, пункт 4 | Каналы с нестандартным кодом будут сохранены... | Аккаунты с нестандартным кодом будут сохранены... |
| Документация на портале разработчика | Необходимо описать список названий каналов, которые поддерживаются... | Необходимо описать список типов аккаунтов, которые поддерживаются... |

## 2. Public API для провайдеров

| Раздел | Текущий термин | Предлагаемая замена |
|--------|---------------|-------------------|
| Теги API | `name: "Каналы"` | `name: "Аккаунты"` |
| Теги API | `description: "Подключение и отключение каналов коммуникаций"` | `description: "Подключение и отключение аккаунтов коммуникаций"` |
| Пути API | `/channels` | `/accounts` |
| Пути API | `/channels/{channelId}` | `/accounts/{accountId}` |
| Параметры | `ChannelId` | `AccountId` |
| Схемы | `ChannelConnectionRequest` | `AccountConnectionRequest` |
| Схемы - ChannelConnectionRequest | `channelId` | `accountId` |
| Схемы - ChannelConnectionRequest | `channelCode` | `accountTypeCode` |
| Схемы - ChannelConnectionRequest | `channelName` | `accountName` |
| Схемы - ChatRequest | `channel` | `accountId` |
| Операции | `connectChannel` | `connectAccount` |
| Операции | `disconnectChannel` | `disconnectAccount` |
| Примеры и описания | Все упоминания "канал" | "аккаунт" (с соответствующим склонением) |

## 3. API для маркетплейса

*В данной спецификации не обнаружено существенных упоминаний термина "канал", требующих замены.*

## 4. API для конфигурации

| Раздел | Текущий термин | Предлагаемая замена |
|--------|---------------|-------------------|
| Структура `ProviderEndpoints` | `getChannels` | `getAccounts` |
| Структура `ProviderEndpoints` | "Эндпоинт получения каналов. Используется для получения списка доступных каналов связи клиента..." | "Эндпоинт получения аккаунтов. Используется для получения списка доступных аккаунтов связи клиента..." |
| Описания | "одноканальные провайдеры" | "одноаккаунтные провайдеры" |
| Описания | "возвращать пустой список каналов" | "возвращать пустой список аккаунтов" |

## 5. Процессы (если будем обновлять)

| Раздел | Текущий термин | Предлагаемая замена |
|--------|---------------|-------------------|
| Все разделы о подключении/отключении каналов | "канал", "каналы" | "аккаунт", "аккаунты" (с соответствующим склонением) |
| Параметры в примерах API запросов | `channelId`, `channelCode`, `channelName` | `accountId`, `accountTypeCode`, `accountName` |
| Описания процессов | "активация/деактивация канала" | "активация/деактивация аккаунта" |

## Примечания

1. При замене необходимо учитывать склонение слов и согласование прилагательных.
2. В некоторых контекстах может потребоваться более глубокая переработка текста для сохранения смысла.
3. В коде и названиях схем/моделей также необходимо произвести соответствующие замены.
4. Термин "тип канала" (`channel_type`) следует заменить на "тип аккаунта" (`account_type`).

## Исключения, где сохраняется термин "канал"

В некоторых контекстах может быть оправдано сохранение термина "канал", если речь идет именно о канале коммуникации в широком смысле, а не о конкретном аккаунте. Например:
- Когда говорится о каналах связи в общем (телефон, email, мессенджеры)
- В описаниях, где "канал" имеет более широкий смысл, чем "аккаунт"

Решение о сохранении термина "канал" в таких случаях должно приниматься в индивидуальном порядке.
