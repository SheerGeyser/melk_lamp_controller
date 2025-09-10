# 🚀 Инструкция по деплою на GitHub Pages

## 📋 Пошаговая настройка

### 1. Создание репозитория на GitHub

1. Перейдите на [GitHub.com](https://github.com)
2. Нажмите **"New repository"** (зеленая кнопка)
3. Заполните поля:
   - **Repository name**: `melk-lamp-controller`
   - **Description**: `MELK Lamp Controller - Web Bluetooth управление умной лампой`
   - **Visibility**: `Public` (для бесплатного GitHub Pages)
   - **Initialize**: ✅ Добавить README, .gitignore, лицензию

### 2. Загрузка кода

```bash
# Клонируйте репозиторий
git clone https://github.com/YOUR_USERNAME/melk-lamp-controller.git
cd melk-lamp-controller

# Скопируйте файлы проекта в папку
cp /path/to/your/project/* .

# Добавьте файлы в git
git add .
git commit -m "Initial commit: MELK Lamp Controller"
git push origin main
```

### 3. Настройка GitHub Pages

**ВАЖНО**: Сначала запустите workflow, затем настройте Pages!

1. Перейдите в **Actions** вкладку репозитория
2. Найдите workflow **"Simple Deploy to GitHub Pages"**
3. Нажмите **"Run workflow"** → **"Run workflow"**
4. Дождитесь завершения (зеленая галочка)

### 4. Активация GitHub Pages

После успешного выполнения workflow:

1. Перейдите в **Settings** → **Pages**
2. В разделе **Source** выберите:
   - **Source**: `GitHub Actions`
3. Нажмите **Save**

**Альтернативный способ** (если первый не работает):
1. В **Settings** → **Pages**
2. **Source**: `Deploy from a branch`
3. **Branch**: `main` или `master`
4. **Folder**: `/ (root)`
5. **Save**

### 5. Проверка деплоя

После успешного деплоя ваше приложение будет доступно по адресу:
```
https://YOUR_USERNAME.github.io/melk-lamp-controller/
```

## 🔧 Структура файлов

```
melk-lamp-controller/
├── .github/
│   └── workflows/
│       └── deploy.yml          # GitHub Actions workflow
├── index.html                  # Главная страница (GitHub Pages)
├── melk_lamp_controller.html   # Оригинальная версия
├── melk_lamp_controller_obfuscated.html  # Обфусцированная версия
├── README.md                   # Документация
├── LICENSE                     # Лицензия
└── DEPLOYMENT.md              # Эта инструкция
```

## ⚙️ Настройки GitHub Pages

### Автоматический деплой
- При каждом push в ветку `main`/`master` происходит автоматический деплой
- Время деплоя: ~2-3 минуты
- Статус можно отслеживать во вкладке **Actions**

### Ручной деплой
```bash
# Внесите изменения в код
git add .
git commit -m "Update: новые функции"
git push origin main

# GitHub Actions автоматически задеплоит изменения
```

## 🔒 Безопасность

### Публичный доступ
- GitHub Pages делает ваш код публично доступным
- Используйте обфусцированную версию для продакшена
- Не храните секретные ключи в коде

### Рекомендации
1. **Используйте `index.html`** как основную страницу
2. **Обфусцированную версию** для дополнительной защиты
3. **Проверяйте** что в коде нет чувствительных данных

## 📱 Тестирование

### Локальное тестирование
```bash
# Запустите локальный сервер
python -m http.server 8000
# или
npx serve .

# Откройте http://localhost:8000
```

### Тестирование на GitHub Pages
1. Откройте https://YOUR_USERNAME.github.io/melk-lamp-controller/
2. Проверьте все функции:
   - ✅ Bluetooth подключение
   - ✅ Управление цветом
   - ✅ Регулировка яркости
   - ✅ Сохранение настроек

## 🐛 Решение проблем

### Деплой не работает
1. Проверьте **Actions** → **Deploy to GitHub Pages**
2. Убедитесь что файл `index.html` существует в корне
3. Проверьте права доступа в **Settings** → **Actions**

### Bluetooth не работает
- GitHub Pages работает только по HTTPS
- Убедитесь что используете современный браузер
- Проверьте что устройство MELK включено

### Стили не загружаются
- Проверьте подключение к интернету
- Tailwind CSS загружается с CDN
- Проверьте консоль браузера на ошибки

## 📞 Поддержка

Если возникли проблемы:
- 📱 **Telegram**: [@BeeDrila](https://t.me/BeeDrila)
- 🐛 **Issues**: Создайте issue в репозитории
- 📧 **Email**: [укажите ваш email]

---

**Удачного деплоя! 🚀**
