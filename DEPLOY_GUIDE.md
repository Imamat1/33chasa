# 🚀 Руководство по развертыванию на Replit

## 📋 Быстрое развертывание

### Шаг 1: Импорт на Replit
1. Зайдите на [replit.com](https://replit.com)
2. Нажмите **"Create"** → **"Import from GitHub"**
3. Вставьте URL вашего GitHub репозитория
4. Выберите **"Full Stack"** template (если доступен)

### Шаг 2: Автоматический запуск
После импорта:
- Replit автоматически установит зависимости
- Настроит переменные окружения
- Инициализирует базу данных
- Запустит приложение

### Шаг 3: Проверка
После запуска проверьте:
- ✅ Сайт открывается по URL Replit
- ✅ API отвечает: `[URL]/api/`
- ✅ Админ-панель: `admin@uroki-islama.ru / admin123`

---

## 🔧 Ручная настройка (если нужно)

### 1. Проверка настройки
```bash
python check_setup.py
```

### 2. Инициализация базы данных
```bash
python init_database.py
```

### 3. Перезапуск сервисов
```bash
bash setup-replit.sh
```

---

## 🌐 Настройка URL

Replit автоматически определяет URL, но если нужно изменить:

### Frontend URL (frontend/.env):
```env
REACT_APP_BACKEND_URL=https://[ваш-replit-домен]
```

### Backend (backend/.env):
```env
SUPABASE_URL=https://kykzqxoxgcwqurnceslu.supabase.co
SUPABASE_ANON_KEY=[ваш-ключ]
SECRET_KEY=uroki-islama-secret-key-2024
```

---

## 🗄️ База данных Supabase

Проект использует готовую базу данных Supabase. При первом запуске автоматически создаются:

### Данные для входа:
- **Админ**: `admin@uroki-islama.ru` / `admin123`
- **Студент**: любой email (создается автоматически)

### Создаются таблицы:
- `admin_users` - Администраторы
- `courses`, `lessons`, `tests` - Учебные материалы
- `students` - Студенты и прогресс
- `team_members` - Команда проекта
- `qa_questions` - Вопросы и ответы имама

---

## 🔍 Диагностика проблем

### Проблема: Сайт не загружается
**Решение:**
```bash
python check_setup.py
supervisorctl status
```

### Проблема: Network Error
**Решение:**
1. Проверьте `frontend/.env`
2. Убедитесь что URL правильный
3. Проверьте работу API: `curl [URL]/api/`

### Проблема: База данных пуста
**Решение:**
```bash
python init_database.py
supervisorctl restart backend
```

### Проблема: Аутентификация не работает
**Решение:**
1. Проверьте настройки Supabase в `backend/.env`
2. Убедитесь что админ создан: `python check_setup.py`
3. Проверьте CORS настройки в `backend/server.py`

---

## 📊 Проверка работы

### API тесты:
```bash
# Основной API
curl https://[URL]/api/

# Курсы
curl https://[URL]/api/courses

# Админ логин
curl -X POST https://[URL]/api/admin/login \
  -H "Content-Type: application/json" \
  -d '{"username":"admin","password":"admin123"}'
```

### Логи:
- Backend: `/tmp/backend.err.log`
- Frontend: `/tmp/frontend.err.log`
- Supervisor: `/tmp/supervisord.log`

---

## 🎯 Особенности Replit

### Автоматические настройки:
- ✅ URL определяется автоматически
- ✅ Зависимости устанавливаются при старте
- ✅ Сервисы запускаются через supervisor
- ✅ HTTPS работает из коробки

### Важные файлы:
- `.replit` - Конфигурация Replit
- `replit.nix` - Системные зависимости
- `setup-replit.sh` - Скрипт инициализации

---

## 🚨 Частые ошибки

### ❌ "Module not found"
**Причина**: Не установлены зависимости
**Решение**: Перезапустите Replit или выполните:
```bash
cd backend && pip install -r requirements.txt
cd ../frontend && yarn install
```

### ❌ "CORS error"
**Причина**: Неправильные CORS настройки
**Решение**: Проверьте `backend/server.py`, должно быть:
```python
allow_origins=["*"]  # или ваш домен
```

### ❌ "Database connection error"
**Причина**: Неправильные настройки Supabase
**Решение**: Проверьте `backend/.env`

---

## 📈 Производительность

### Для лучшей работы на Replit:
1. **Используйте Replit Pro** для стабильной работы
2. **Не выключайте Replit** надолго (может потребоваться перезапуск)
3. **Регулярно проверяйте логи** на ошибки

### Мониторинг:
```bash
# Статус сервисов
supervisorctl status

# Использование памяти
free -h

# Активные соединения
netstat -tlnp
```

---

## ✅ Финальная проверка

После развертывания убедитесь что работает:

- [ ] 🌐 Главная страница загружается
- [ ] 📚 Курсы отображаются  
- [ ] 👤 Вход в админ-панель работает
- [ ] ❓ Q&A раздел функционирует
- [ ] 🏆 Лидерборд показывает данные
- [ ] 📊 API возвращает JSON

**Готово! Ваш проект "Уроки Ислама" успешно развернут на Replit! 🎉**