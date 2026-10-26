# 🦊 KITSU Esports — Official Website

[![Security Policy](https://img.shields.io/badge/Security-Policy-brightgreen.svg)](SECURITY.md)
[![Game](https://img.shields.io/badge/Counter--Strike%202-Esports-FF4A1C.svg)](https://t.me/kitsues)
[![Domain](https://img.shields.io/badge/Domain-kitsuesports.space-FF4A1C.svg)](https://kitsuesports.space/)
[![Vercel](https://img.shields.io/badge/Deploy-Vercel-black.svg)](https://vercel.com/)
[![Cloudflare](https://img.shields.io/badge/CDN-Cloudflare-F38020.svg)](https://cloudflare.com/)

Официальный веб-сайт и бренд-портал киберспортивной организации **KITSU Esports** по Counter-Strike 2.  
Домен проекта: [kitsuesports.space](https://kitsuesports.space/)

---

## 🇷🇺 О проекте

**KITSU Esports** — российская киберспортивная организация по Counter-Strike 2, основанная 20 сентября 2026 года.
- **Ростер CS2**:
  - 💥 `y9ko` — Entry Fragger (Энтри-фрагер)
  - 🧠 `hays0n` — In-Game Leader (Капитан / Игровой лидер)
  - 🎯 `st1n3x` — Support (Саппорт)
  - 🛡️ `qyurix` — Anchor (Опорник)
  - ⚡ `Famlikus` — AWPer (AWP-снайпер)
  - 🔄 `a1eks` — Substitute (Запасной игрок)
- **Матчи и расписание**: динамический трекер предстоящих и завершённых игр с определением времени по МСК.
- **Новости**: оперативная лента анонсов, трансферов и турниров.
- **Пресс-кит (Press Kit)**: фирменная символика, экспорт векторных (SVG) и растровых (PNG 1800px) логотипов, интерактивная палитра цветов в 1 клик (`#FF4A1C`, `#000000`, `#131313`, `#FFFFFF`).
- **Двуязычность**: мгновенное переключение RU / EN с сохранением выбора пользователя в `localStorage`.

---

## 🔍 Оптимизация для Google и поисковых систем (SEO)

Портал подготовлен для моментального распознавания поисковыми роботами Google, Yandex и Bing как официальная киберспортивная организация:

1. **Разметка Schema.org JSON-LD (Knowledge Graph)**:
   - Внедрена семантическая сущность `["SportsTeam", "Organization"]`.
   - Описаны состав игроков (`athlete`), их роли (IGL, Entry, AWPer, Anchor, Support), дата основания команды (20 сентября 2026 г.) и спортивная дисциплина (`Counter-Strike 2`).
   - Связаны официальные социальные сети через `sameAs` (Telegram, VK, Steam, YouTube, GitHub), что необходимо Google для формирования официального блока знаний (Knowledge Panel).
2. **Open Graph & Twitter Cards**:
   - Настроены превью сгенерированным баннером `og-image.png` (1200x630) для привлекательного отображения ссылок в Telegram, VK, Discord, Twitter и поисковиках.
3. **Карта сайта (Sitemap) и Robots**:
   - `sitemap.xml`: проиндексированы все разделы и языковые версии.
   - `robots.txt`: открыт доступ поисковым ботам, указан адрес sitemap и канонический хост `https://kitsuesports.space`.
4. **Канонический URL**:
   - Указан `<link rel="canonical" href="https://kitsuesports.space/">`.

---

## 🛡️ Безопасность и заголовки (Security)

- **Content Security Policy (CSP)**: запрет внедрения посторонних скриптов, защита от XSS.
- **Защита от кликджекинга**: заголовок `X-Frame-Options: DENY`, `frame-ancestors 'none'` и скрипт frame-busting.
- **Защита от Reverse Tabnabbing**: атрибуты `rel="noopener noreferrer"` на всех внешних ссылках.
- **HSTS & Permissions Policy**: принудительный HTTPS и отключение неиспользуемых браузерных API.
- Подробности в файле [SECURITY.md](SECURITY.md).

---

## 🚀 Развёртывание: Vercel + Cloudflare

### 1. Подключение к Vercel
1. Перейдите на [vercel.com](https://vercel.com) и импортируйте репозиторий `derut65/kitsu-esports-`.
2. Framework Preset: **Other** (чистый HTML/JS/CSS).
3. Нажмите **Deploy**. Проект автоматически использует файл конфигурации `vercel.json`.

### 2. Привязка домена `kitsuesports.space` в Cloudflare и Vercel
1. В панели **Vercel** ➔ проект ➔ **Settings** ➔ **Domains**:
   - Добавьте `kitsuesports.space` и `www.kitsuesports.space`.
2. В панели **Cloudflare** ➔ DNS:
   - Создайте запись **A**: `name: @`, `IPv4: 76.76.21.21`, Proxy status: **Proxied (оранжевое облако)**.
   - Создайте запись **CNAME**: `name: www`, `Target: cname.vercel-dns.com` (или `@`), Proxy status: **Proxied**.
3. В панели **Cloudflare** ➔ **SSL/TLS**:
   - Установите режим шифрования: **Full (strict)** *(важно для предотвращения бесконечного редиректа!)*.

### 3. Регистрация в Google Search Console
1. Откройте [Google Search Console](https://search.google.com/search-console).
2. Добавьте ресурс: домен `kitsuesports.space`.
3. Подтвердите владение через DNS-запись TXT в Cloudflare (или HTML-тег).
4. В разделе **Sitemaps (Файлы Sitemap)** отправьте: `https://kitsuesports.space/sitemap.xml`.
5. Запросите индексирование главной страницы `https://kitsuesports.space/`.

---

## 📂 Структура проекта

```text
├── index.html        # Главный файл сайта с SEO-разметкой и CSP
├── vercel.json       # Конфигурация заголовков и кэширования для Vercel
├── sitemap.xml       # Карта сайта для Google и Yandex
├── robots.txt        # Инструкции для поисковых роботов
├── logo.svg          # Официальный векторный логотип
├── favicon.svg       # Иконка сайта (Favicon)
├── og-image.png      # Баннер предпросмотра соцсетей (1200x630)
├── SECURITY.md       # Политика безопасности
├── README.md         # Документация проекта
└── .gitignore        # Список исключений Git
```

---

## 🦊 Контакты / Contacts

- **Официальный сайт**: [kitsuesports.space](https://kitsuesports.space)
- **Telegram-канал**: [@kitsues](https://t.me/kitsues)
- **VK**: [vk.com/kitsues](https://vk.com/kitsues)
- **Email**: [kitsuesports@gmail.com](mailto:kitsuesports@gmail.com)
- **Менеджер Telegram**: [@kitsuadmin](https://t.me/kitsuadmin)
- **YouTube**: [@kitsu-esports](https://youtube.com/@kitsu-esports)
- **Steam Community**: [steamcommunity.com/groups/kitsuesports](https://steamcommunity.com/groups/kitsuesports)
