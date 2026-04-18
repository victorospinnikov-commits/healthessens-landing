# Healthessens Landing

Минималистичный одностраничный лендинг бренда **Healthessens** — БАДы для иммунитета, сна и красоты.

**Live:** https://healthessens.ru

## Стек

- Один статичный файл `index.html` — чистый HTML + CSS + vanilla JS.
- Без сборщиков, без npm-зависимостей, без фреймворков.
- Все стили и скрипты inline в `<style>` и `<script>`.

## Структура страницы

1. **Splash** — полноэкранный сплэш с логотипом, исчезает при первом скролле и больше не появляется.
2. **Navigation** — залипающий топ с CTA.
3. **Hero** — «Поддержка, которую ты не замечаешь» + кнопка «Подобрать комплекс».
4. **Принцип** — 4 карточки: дозировки, состав, научный подход, цена.
5. **Продукты** — 4 карточки: Магний B6, D3+K2, Омега-3, Селен.
6. **Как это работает** — 3 шага.
7. **Квиз** — CTA-плашка с переходом на тест.
8. **Footer**.

## Палитра

| Токен | HEX | Применение |
|---|---|---|
| `--bg` | `#faf9f6` | фон страницы |
| `--surface` | `#ffffff` | карточки |
| `--ink` | `#1a1a1a` | основной текст |
| `--accent` | `#2d5a4b` | шалфей, CTA |
| `--terra` | `#c76b4a` | акцент в градиенте квиза |

Шрифт: `Inter, -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif`.

## Адаптив

- `≥1100px` — 4 колонки.
- `720–1100px` — 2 колонки.
- `≤720px` — 1 колонка, уменьшённые отступы.

## Локальный превью

```bash
# Любой статичный сервер подойдёт:
python -m http.server 8000
# или
npx serve .
# или (Windows без Node/Python) PowerShell-сервер из .claude/serve.ps1
powershell -NoProfile -ExecutionPolicy Bypass -File .claude/serve.ps1 -Port 3000
```

Открой http://localhost:3000.

## Deploy

Деплой через `git pull` на сервере:

```bash
ssh root@<server>
cd /var/www/healthessens
git pull
chown -R www-data:www-data .
```

Nginx обслуживает `/var/www/healthessens` с gzip, кэшем `/assets/` на 30 дней, TLS от Let's Encrypt (автопродление через `certbot.timer`).

## Структура

```
.
├── index.html         # весь лендинг
├── assets/            # изображения продуктов (PNG, прозрачный фон)
│   ├── product-1.png  # Магний B6
│   ├── product-2.png  # Витамин D3+K2
│   ├── product-3.png  # Селен
│   └── product-4.png  # Омега-3
├── README.md
└── .gitignore
```

## Лицензия

Приватный проект. Все права — Healthessens, 2024.
