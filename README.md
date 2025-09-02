
<!-- AUTOGEN:STATS -->


## 📊 Статистика GitHub :

[![📊 Views](https://img.shields.io/endpoint?url=https://raw.githubusercontent.com/VuToV-Mykola/screenshot-visitor-like-workflow/main/assets/db/visitors-badge.json)](https://github.com/VuToV-Mykola/screenshot-visitor-like-workflow/graphs/traffic)
[![⭐ Stars](https://img.shields.io/endpoint?url=https://raw.githubusercontent.com/VuToV-Mykola/screenshot-visitor-like-workflow/main/assets/db/likes-badge.json)](https://github.com/VuToV-Mykola/screenshot-visitor-like-workflow/actions/workflows/screenshot-and-visitor.yaml)
[![📦 Size](https://img.shields.io/endpoint?url=https://raw.githubusercontent.com/VuToV-Mykola/screenshot-visitor-like-workflow/main/assets/db/repo-size.json)](https://github.com/VuToV-Mykola/screenshot-visitor-like-workflow)
[![📄 License](https://img.shields.io/endpoint?url=https://raw.githubusercontent.com/VuToV-Mykola/screenshot-visitor-like-workflow/main/assets/db/repo-license.json)](https://github.com/VuToV-Mykola/screenshot-visitor-like-workflow/blob/main/LICENSE)
<!-- 📸 Скріншот проекту закоментований -->
<!-- END:AUTOGEN -->

# 🚀 Інструкція з перенесення Screenshot & Visitor Workflow

Цей workflow автоматично створює скриншоти веб-сторінок, відстежує відвідувачів, керує лайками та генерує технологічні бейджі для будь-якого GitHub репозиторію.

## 📋 Що робить workflow

- 📸 **Автоматичні скриншоти** - створює скриншоти GitHub Pages або локального index.html
- 👀 **Відстеження відвідувачів** - показує реальну кількість унікальних відвідувачів
- ⭐ **Розумна система лайків** - GitHub зірки + мануальні лайки від не-авторів зірок
- 🛠 **Технологічні бейджі** - автоматично детектує та показує використовувані технології
- 📦 **Статистика релізів** - показує кількість завантажень релізів (якщо є)
- 👥 **Збереження користувачів** - детальна інформація про stargazers та лайкерів
- 🔄 **Автооновлення README** - додає бейджі та скриншот до README.md
- ⏰ **Регулярні оновлення** - запускається кожні 2 години та при push

## 🛠 Крок 1: Копіювання файлів

### 1.1 Створіть workflow файл

Створіть файл `.github/workflows/screenshot-and-visitor.yaml` у вашому репозиторії та скопіюйте вміст з `screenshot-and-visitor-template.yaml`.

### 1.2 Структура файлів (створюється автоматично)

### 3. Структура папок

Workflow автоматично створить наступну структуру:

### 3. Структура папок

Workflow автоматично створить наступну структуру:

~~~text
assets/
├── db/
│   ├── visitors-badge.json      # Бейдж відвідувачів
│   ├── likes-badge.json         # Бейдж лайків
│   ├── stargazers.json          # Детальна інформація про користувачів зірок
│   ├── manual-likes.json        # Мануальні лайки
│   └── unique-users.json        # Загальна статистика користувачів
└── screenshot.png               # Автоматичний скриншот
~~~

## 🔑 Крок 2: Налаштування дозволів (Автоматично)

**Хороші новини!** Workflow тепер використовує вбудований `GITHUB_TOKEN` з автоматичними дозволами. Не потрібно створювати Personal Access Token!

### Автоматичні дозволи:

- ✅ `contents: write` - для оновлення файлів
- ✅ `pages: read` - для доступу до GitHub Pages
- ✅ `actions: read` - для читання workflow

## 📝 Крок 3: Підготовка README.md

### 3.1 Додайте маркери до README.md

~~~text

<!-- AUTOGEN:STATS -->
<!-- Тут автоматично з'являться бейджі та скриншот -->
~~~
# Ваш проект

Опис вашого проекту... 

### 3.2 Приклад згенерованого контенту

Workflow автоматично додасть:

- 📊 Бейдж відвідувачів
- ⭐ Бейдж лайків (зірки + мануальні)
- 🛠 Технологічні бейджі (HTML5, CSS3, JavaScript, тощо)
- 💻 Інструменти (VS Code, GitHub, Figma)
- 📦 Статистика репозиторію (розмір, мова, ліцензія)
- 📥 Завантаження релізів (якщо є)
- 📸 Актуальний скриншот

## 🌐 Крок 4: Налаштування GitHub Pages

### 4.1 Увімкнення GitHub Pages

1. Settings репозиторію → Pages
2. Source: "Deploy from a branch"
3. Branch: `main` (або `master`)
4. Folder: `/ (root)`
5. Натисніть "Save"

### 4.2 Перевірка URL

Ваш сайт буде доступний за адресою: `https://YOUR_USERNAME.github.io/YOUR_REPOSITORY_NAME/`

## ⚙️ Крок 5: Налаштування змінних середовища (опціонально)
~~~text
env:
  SCREENSHOT_WIDTH: 1920          # Ширина скриншоту
  SCREENSHOT_HEIGHT: 1080         # Висота скриншоту (авто для fullPage)
  BADGE_STYLE: for-the-badge      # Стиль бейджів
  BADGE_COLOR: brightgreen        # Колір бейджу відвідувачів
  LIKES_COLOR: gold               # Колір бейджу лайків
  DATA_DIR: assets/db             # Папка для збереження даних
  SCREENSHOT_DIR: assets          # Папка для скриншоту
  SCREENSHOT_SELECTOR: ""         # CSS селектор (порожній = вся сторінка)
~~~
## 🚀 Крок 6: Запуск workflow

### 6.1 Автоматичний запуск

- При push до main/master гілки
- Кожні 2 години (за розкладом)
- При створенні нових релізів

### 6.2 Ручний запуск з лайком

1. Actions → "Auto-update: visitors, likes, and screenshot"
2. "Run workflow"
3. Поставте галочку "Add your like" для додавання лайка
4. "Run workflow"

## ⭐ Крок 7: Розумна система лайків

### 7.1 Як працює

- **Зірки GitHub** = автоматично враховуються
- **Мануальні лайки** = тільки від користувачів, які НЕ є авторами зірок
- **Загальна кількість** = зірки + унікальні мануальні лайки

### 7.2 Додавання лайка

Користувачі можуть додати лайк через workflow dispatch або поставивши зірку репозиторію.

## 🛠 Крок 8: Технологічні бейджі

### 8.1 Автоматичне детектування

Workflow автоматично детектує:

- **Мови програмування** (через GitHub API)
- **Файли проектів** (HTML, CSS, JS, тощо)
- **Стандартні інструменти** (VS Code, GitHub, Figma)

### 8.2 Підтримувані технології

- HTML5, CSS3, JavaScript, TypeScript
- Node.js, React, Vue, Angular
- Sass, Less, Bootstrap
- VS Code, GitHub, Figma

## 📦 Крок 9: Релізи та завантаження

Якщо у вашому репозиторії є релізи, workflow автоматично:

- Підраховує загальну кількість завантажень
- Створює бейдж з цією статистикою
- Оновлює інформацію при нових релізах

## 🔧 Налаштування для різних типів проектів

### 9.1 Для статичних сайтів

- Переконайтеся, що `index.html` знаходиться в корені
- Увімкніть GitHub Pages

### 9.2 Для React/Vue/Angular проектів

- Налаштуйте збірку в папку `dist` або `build`
- Змініть налаштування GitHub Pages на відповідну папку

### 9.3 Для документації

- Workflow працює з будь-якими HTML сторінками
- Сумісний з Jekyll, GitBook, Docusaurus тощо

## 🐛 Усунення проблем

### Помилка permissions

- Переконайтеся, що в Settings → Actions → General увімкнено "Read and write permissions"

### Бейджі показують "resource not found"

- Зачекайте завершення першого запуску workflow
- Перевірте, що файли створені в папці `assets/db/`

### Скриншот не створюється

- Перевірте, що GitHub Pages працює та доступний
- Переконайтеся, що `index.html` існує та відображається

### Технологічні бейджі не з'являються

- Workflow детектує технології автоматично через GitHub API
- Переконайтеся, що репозиторій містить відповідні файли

## 📊 Моніторинг та аналітика

### Детальна статистика

- `stargazers.json` - список користувачів зі зірками
- `manual-likes.json` - мануальні лайки
- `unique-users.json` - загальна статистика користувачів
- `stats-data.json` - повна статистика репозиторію

### Перегляд логів

Actions → "Auto-update: visitors, likes, and screenshot" → останній запуск

## 🎨 Кастомізація

### Стилі бейджів

- `flat` - плоский стиль
- `flat-square` - плоский квадратний
- `for-the-badge` - великі бейджі (рекомендовано)
- `plastic` - пластиковий ефект
- `social` - соціальний стиль

### Кольори

- `brightgreen`, `green`, `yellowgreen`, `yellow`
- `orange`, `red`, `lightgrey`, `blue`, `gold`

## 🔄 Оновлення workflow

Для оновлення до нової версії:

1. Замініть вміст `.github/workflows/screenshot-and-visitor.yaml`
2. Скопіюйте новий вміст з `screenshot-and-visitor-template.yaml`
3. Workflow автоматично адаптується до нових функцій

## 📞 Підтримка

При виникненні проблем:

1. Перевірте Actions → Logs для деталей
2. Переконайтеся, що GitHub Pages працює
3. Перевірте права доступу в Settings → Actions

---

**Готово!** Ваш репозиторій тепер має повну автоматизацію з розумними лайками, технологічними бейджами та детальною аналітикою! 🎉
