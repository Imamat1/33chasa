# 📁 Подготовка для GitHub

## 🚀 Быстрая загрузка на GitHub

### 1. Создание репозитория
1. Зайдите на [github.com](https://github.com)
2. Нажмите **"New repository"**
3. Название: `uroki-islama`
4. Описание: `Образовательная платформа для изучения основ ислама`
5. Выберите **Public** или **Private**
6. ✅ Добавьте README
7. ✅ Добавьте .gitignore (Node)
8. Нажмите **"Create repository"**

### 2. Загрузка кода
```bash
# В вашей локальной папке с проектом
git init
git add .
git commit -m "Initial commit: Образовательная платформа Уроки Ислама"
git branch -M main
git remote add origin https://github.com/[ваш-username]/uroki-islama.git
git push -u origin main
```

### 3. Проверка загрузки
Убедитесь что загружены все файлы:
- ✅ `/backend/` - FastAPI сервер
- ✅ `/frontend/` - React приложение  
- ✅ `.replit` - Конфигурация Replit
- ✅ `setup-replit.sh` - Скрипт настройки
- ✅ `init_database.py` - Инициализация БД
- ✅ `README.md` - Документация

---

## 🔄 Развертывание на Replit

### Из GitHub на Replit:
1. **Replit** → **"Create"** → **"Import from GitHub"**
2. Вставьте: `https://github.com/[ваш-username]/uroki-islama`
3. Template: **"Full Stack"** (если доступен)
4. Нажмите **"Import"**

### Автоматический запуск:
Replit автоматически:
- ✅ Установит зависимости
- ✅ Настроит URL
- ✅ Запустит базу данных
- ✅ Создаст админа и контент

---

## 📋 Важные файлы для GitHub

### Обязательные файлы:
```
uroki-islama/
├── .replit                    # ← Конфигурация Replit
├── replit.nix                # ← Системные зависимости
├── setup-replit.sh           # ← Скрипт автонастройки
├── init_database.py          # ← Инициализация БД
├── check_setup.py            # ← Диагностика
├── README.md                 # ← Документация
├── DEPLOY_GUIDE.md           # ← Руководство развертывания
├── .gitignore                # ← Исключения Git
├── package.json              # ← Метаданные проекта
├── backend/
│   ├── server.py             # ← FastAPI сервер
│   ├── models.py             # ← Модели данных
│   ├── supabase_client.py    # ← Клиент БД
│   ├── requirements.txt      # ← Python зависимости
│   └── .env                  # ← Настройки Supabase
└── frontend/
    ├── src/                  # ← React компоненты
    ├── package.json          # ← Node зависимости
    └── .env                  # ← URL настройки
```

### Файлы для исключения (.gitignore):
- `node_modules/`
- `__pycache__/`
- `uploads/`
- `*.log`
- `/tmp/`

---

## 🌟 Особенности проекта

### Технологии:
- **Backend**: FastAPI + Python 3.10
- **Frontend**: React 18 + Tailwind CSS
- **Database**: Supabase (PostgreSQL)
- **Deploy**: Replit (автоматически)

### Функции:
- 🕌 Курсы по исламу
- 📝 Интерактивные тесты
- ❓ Q&A система
- 👥 Управление командой
- 🏆 Лидерборд студентов
- ⚙️ Админ-панель

### Готовые данные:
- 👤 Админ: `admin@uroki-islama.ru / admin123`
- 📚 Демо-курс "Основы ислама"
- ❓ Примеры Q&A
- 👥 Команда преподавателей

---

## 🔧 Кастомизация

### Изменение Supabase:
1. Создайте проект на [supabase.com](https://supabase.com)
2. Обновите `backend/.env`:
   ```env
   SUPABASE_URL=https://[ваш-проект].supabase.co
   SUPABASE_ANON_KEY=[ваш-ключ]
   ```

### Добавление контента:
1. Войдите как админ на сайте
2. Используйте админ-панель для:
   - Создания курсов
   - Добавления уроков
   - Настройки команды
   - Управления Q&A

### Изменение дизайна:
- Основные стили: `frontend/src/App.css`
- Tailwind: `frontend/tailwind.config.js`
- Компоненты: `frontend/src/components.js`

---

## 📞 Поддержка

### При проблемах:
1. **Проверка**: `python check_setup.py`
2. **Логи**: Смотрите в Replit консоль
3. **База данных**: `python init_database.py`
4. **GitHub Issues**: Создайте issue в репозитории

### Контакты:
- 📧 **Email**: admin@uroki-islama.ru
- 🐛 **Баги**: GitHub Issues
- 💬 **Вопросы**: Replit комментарии

---

**Готово! Ваш проект готов к загрузке на GitHub и развертыванию на Replit! 🎉**