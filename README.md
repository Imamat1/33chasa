# 🕌 Уроки Ислама - Образовательная платформа

Современная веб-платформа для изучения основ ислама с интерактивными уроками, тестами и системой прогресса.

## 🚀 Быстрый старт на Replit

### 1. Импорт проекта
1. Откройте [Replit](https://replit.com)
2. Нажмите "Create" → "Import from GitHub"
3. Вставьте URL вашего репозитория
4. Выберите "Full Stack" template

### 2. Автоматическая настройка
После импорта Replit автоматически:
- Установит все зависимости
- Настроит переменные окружения
- Инициализирует базу данных
- Запустит приложение

### 3. Доступ к приложению
- **Веб-сайт**: по URL Replit (отображается в верхней части)
- **Админ-панель**: admin@uroki-islama.ru / admin123
- **API**: `https://[ваш-url]/api/`

## 🛠️ Локальная разработка

### Требования
- Python 3.10+
- Node.js 18+
- Yarn

### Установка
```bash
# Клонировать репозиторий
git clone [URL-репозитория]
cd uroki-islama

# Запустить настройку
bash setup-replit.sh
```

## 🏗️ Архитектура

```
📁 uroki-islama/
├── 🐍 backend/          # FastAPI сервер
│   ├── server.py        # Основной сервер
│   ├── models.py        # Модели данных
│   ├── supabase_client.py # Клиент БД
│   └── requirements.txt # Python зависимости
├── ⚛️ frontend/         # React приложение
│   ├── src/            # Исходный код
│   ├── public/         # Статические файлы
│   └── package.json    # Node зависимости
├── 🗄️ init_database.py # Инициализация БД
├── ⚙️ setup-replit.sh  # Скрипт настройки
└── 📋 .replit          # Конфигурация Replit
```

## 💾 База данных

Проект использует **Supabase** (PostgreSQL) со следующими таблицами:
- `admin_users` - Администраторы
- `courses` - Курсы
- `lessons` - Уроки
- `tests` - Тесты
- `questions` - Вопросы тестов
- `students` - Студенты
- `team_members` - Команда
- `qa_questions` - Вопросы и ответы имама

## 🔧 Конфигурация

### Переменные окружения

**Backend (.env):**
```env
SUPABASE_URL=your_supabase_url
SUPABASE_ANON_KEY=your_anon_key
SECRET_KEY=your_secret_key
```

**Frontend (.env):**
```env
REACT_APP_BACKEND_URL=https://your-replit-url
```

## 📱 Функции

### Для студентов:
- 📚 Изучение курсов и уроков
- 📝 Прохождение тестов
- 🏆 Система баллов и лидерборд
- ❓ Вопросы и ответы имама
- 👤 Автоматическая регистрация

### Для администраторов:
- ⚙️ Управление курсами и уроками
- 📊 Создание тестов и вопросов
- 👥 Управление командой
- 📈 Статистика и аналитика
- 🔧 Настройка Q&A системы

## 🎯 API Эндпоинты

### Аутентификация
- `POST /api/auth/login` - Универсальный вход
- `POST /api/admin/login` - Вход администратора

### Курсы
- `GET /api/courses` - Список курсов
- `GET /api/courses/{id}/lessons` - Уроки курса
- `GET /api/lessons/{id}` - Детали урока

### Тесты
- `POST /api/tests/{id}/start-session` - Начать тест
- `POST /api/test-sessions/{id}/submit` - Отправить ответы

### Q&A
- `GET /api/qa/questions` - Вопросы и ответы
- `GET /api/qa/categories` - Категории
- `GET /api/qa/featured` - Рекомендуемые

### Администрирование
- `GET /api/admin/dashboard` - Статистика
- `POST /api/admin/courses` - Создать курс
- `POST /api/admin/lessons` - Создать урок

## 🔄 Обновление

```bash
# Получить последние изменения
git pull origin main

# Обновить зависимости
cd backend && pip install -r requirements.txt
cd ../frontend && yarn install

# Перезапустить на Replit
# Нажмите кнопку "Run" в Replit
```

## 🐛 Отладка

### Проверка работы:
```bash
# API статус
curl https://[ваш-url]/api/

# Список курсов
curl https://[ваш-url]/api/courses

# Тест админ логина
curl -X POST https://[ваш-url]/api/admin/login \
  -H "Content-Type: application/json" \
  -d '{"username":"admin","password":"admin123"}'
```

### Логи:
- Backend: `/tmp/backend.err.log`
- Frontend: `/tmp/frontend.err.log`
- Supervisor: `/tmp/supervisord.log`

## 👥 Команда

- **Али Евтеев** - Этика
- **Абдуль-Басит Микушкин** - Основы веры
- **Алексей Котенев** - Практика веры
- **Микаиль Ганиев** - История

## 📄 Лицензия

Этот проект создан для образовательных целей.

## 🤝 Поддержка

- 📧 Email: admin@uroki-islama.ru
- 🐛 Issues: GitHub Issues
- 💬 Чат: Replit комментарии

---

**Сделано с ❤️ для мусульманской общины**