# 🦊 KITSU Esports — Official Website

[![Security Policy](https://img.shields.io/badge/Security-Policy-brightgreen.svg)](SECURITY.md)
[![Game](https://img.shields.io/badge/Counter--Strike%202-Esports-FF4A1C.svg)](https://t.me/kitsues)
[![License](https://img.shields.io/badge/License-MIT-black.svg)](#лицензия--license)
[![Status](https://img.shields.io/badge/Status-Active-success.svg)](https://derut65.github.io/kitsu-esports-/)

Официальный веб-сайт и бренд-портал киберспортивной организации **KITSU Esports** по Counter-Strike 2.  
Official website and brand portal of the **KITSU Esports** Counter-Strike 2 organization.

---

## 🇷🇺 О проекте

**KITSU Esports** — молодая и амбициозная киберспортивная организация по Counter-Strike. Портал разработан в соответствии с современными стандартами веб-разработки и кибербезопасности:
- **Состав команды**: карточки игроков основного состава (`y9ko`, `hays0n`, `st1n3x`, `qyurix`, `Famlikus`) и запасного (`a1eks`).
- **Матчи и расписание**: динамический трекер предстоящих и прошедших встреч с автоматическим определением времени по МСК.
- **Новости**: лента анонсов, трансферов и турнирных новостей.
- **Пресс-кит (Press Kit)**: фирменная символика, экспорт векторных (SVG) и растровых (PNG высокого разрешения) логотипов прямо из браузера, интерактивная палитра цветов в 1 клик (`#FF4A1C`, `#000000`, `#131313`, `#FFFFFF`).
- **Двуязычность**: мгновенное переключение RU / EN с сохранением выбора пользователя.
- **Быстродействие**: ультра-легковесный монолитный HTML5/CSS3/Vanilla JS без внешних тяжёлых фреймворков.

---

## 🛡️ Безопасность / Security

Проект защищён в соответствии с рекомендациями OWASP:

1. **Content Security Policy (CSP)**:
   - Ограничение источников скриптов и стилей (`'self'`, `'unsafe-inline'`, Google Fonts).
   - Запрет несанкционированных сетевых запросов (`connect-src 'self'`).
   - Блокировка плагинов и опасных объектов (`object-src 'none'`).
   - Защита от манипуляций базовым URL (`base-uri 'self'`).
   - Принудительное обновление до HTTPS (`upgrade-insecure-requests`).
2. **Защита от кликджекинга (Clickjacking)**:
   - Заголовок `X-Frame-Options: DENY`.
   - Защитный скрипт frame-busting (блокировка отображения страницы во фреймах сторонних сайтов).
3. **Защита от обратного табнаббинга (Reverse Tabnabbing)**:
   - Все внешние ссылки содержат обязательные атрибуты `rel="noopener noreferrer" target="_blank"`.
4. **Защита от MIME-sniffing**:
   - `X-Content-Type-Options: nosniff`.
5. **Политика конфиденциальности реферера**:
   - `Referrer-Policy: strict-origin-when-cross-origin`.
6. **Ограничение аппаратных API (Permissions Policy)**:
   - Отключён доступ к камере, микрофону, геолокации, платежам и датчикам движения.
7. **Санитизация DOM и маршрутизации**:
   - Очистка хеша URL (`location.hash`) от спецсимволов для предотвращения DOM-инъекций.
   - Валидация входных данных языка (`setLang`).
   - Безопасная очистка `Blob URL` (`URL.revokeObjectURL`) при экспорте логотипов.

Подробная информация о политике безопасности и контакты для сообщений об уязвимостях доступны в [SECURITY.md](SECURITY.md).

---

## 📂 Структура репозитория

```text
├── index.html        # Основной веб-портал с полным функционалом и защитой
├── SECURITY.md       # Политика безопасности и контактная информация
├── README.md         # Документация проекта
├── robots.txt        # Правила индексации для поисковых систем
└── .gitignore        # Список исключений Git
```

---

## 🚀 Запуск и публикация

### Локальный просмотр
Достаточно просто открыть файл `index.html` в любом современном веб-браузере:
```bash
# Windows PowerShell
Start-Process index.html
```
Или использовать локальный веб-сервер:
```bash
npx serve .
# или Python:
python -m http.server 8000
```

### Публикация на GitHub Pages
1. Перейдите в настройки репозитория: **Settings** -> **Pages**.
2. В секции **Build and deployment** выберите:
   - **Source**: `Deploy from a branch`
   - **Branch**: `main`, папка `/ (root)`
3. Нажмите **Save**. Сайт будет автоматически доступен по адресу:  
   👉 `https://derut65.github.io/kitsu-esports-/`

---

## 🦊 Контакты / Contacts

- **Telegram-канал**: [@kitsues](https://t.me/kitsues)
- **VK**: [vk.com/kitsues](https://vk.com/kitsues)
- **Email**: [kitsuesports@gmail.com](mailto:kitsuesports@gmail.com)
- **Менеджер Telegram**: [@kitsuadmin](https://t.me/kitsuadmin)
- **Steam Community**: [steamcommunity.com/groups/kitsuesports](https://steamcommunity.com/groups/kitsuesports)

---

## 📄 Лицензия / License

© 2026 KITSU Esports. Все права защищены / All rights reserved.
