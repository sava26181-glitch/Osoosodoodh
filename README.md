# Claude Telegram File Agent

Полноценный Telegram-бот на webhook + Claude API + Render.

## Генерация файлов

Бот умеет создавать и отправлять:

- `.txt`
- `.md`
- `.py`
- `.js`
- `.ts`
- `.html`
- `.css`
- `.json`
- `.csv`
- `.xml`
- `.sql`
- `.yaml`
- `.yml`
- `.sh`
- `.java`
- `.cpp`
- `.c`
- `.h`
- `.php`
- `.go`
- `.rs`
- `.jsx`
- `.tsx`
- `.xlsx`
- `.docx`
- `.pdf`
- `.zip`

## Как пользоваться

Напиши боту обычную команду:

> Создай Python-скрипт, который переименовывает все JPG в папке и отправь мне.

Или:

> Сделай Excel с таблицей расходов: еда 300, транспорт 100, жильё 1000.

Или:

> Создай PDF-инструкцию по установке Python на русском.

Или:

> Создай простой сайт-визитку и упакуй HTML, CSS и JS в ZIP.

Claude определяет, что нужен файл, а Python создаёт файл соответствующего формата и Telegram отправляет его.

## Deploy на Render

1. Загрузи проект в GitHub.
2. В Render выбери New -> Blueprint.
3. Подключи GitHub repository.
4. Заполни `TELEGRAM_BOT_TOKEN` и `ANTHROPIC_API_KEY`.
5. `WEBHOOK_SECRET` Render сгенерирует автоматически.
6. Нажми Deploy.

Render URL автоматически используется как webhook URL.

## Health

`/health` возвращает:

`{"status":"ok"}`

## Ограничение

Память диалога хранится в RAM. При перезапуске Render она сбрасывается.

Для постоянной памяти можно подключить PostgreSQL.

## Безопасность

Никогда не публикуй `.env`, Telegram token или Anthropic API key в GitHub.
