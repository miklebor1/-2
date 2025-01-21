# Telegram Bot: Маркетплейс айфонов

Этот проект представляет собой Telegram-бота, который позволяет искать, заказывать и управлять заказами на айфоны.

## Функциональность

- **Приветствие и запуск**: Команда `/start` приветствует пользователя и предоставляет краткое описание функционала бота.
- **Поиск моделей кроссовок**: Пользователь может найти модели кроссовок, отправив текстовый запрос (например, "Поиск: iPhone 14").
- **Оформление заказа**: Команда `/order` оформляет заказ для пользователя.
- **Проверка статуса заказа**: Команда `/status` позволяет узнать статус текущего заказа.
- **Отмена заказа**: Команда `/cancel` отменяет текущий заказ пользователя.

## Установка

1. Склонируйте репозиторий или загрузите код проекта:
    ```bash
    git clone https://github.com/ваш-репозиторий.git
    cd ваш-репозиторий
    ```

2. Создайте и активируйте виртуальное окружение:
    ```bash
    python3 -m venv .venv
    source .venv/bin/activate  # Для Linux/macOS
    .venv\Scripts\activate     # Для Windows
    ```

3. Установите зависимости:
    ```bash
    pip install -r requirements.txt
    ```

4. Убедитесь, что у вас установлен модуль `nest_asyncio`, который позволяет работать с существующими циклами событий в асинхронных приложениях:
    ```bash
    pip install nest_asyncio
    ```

5. Создайте и настройте Telegram-бота с помощью [BotFather](https://core.telegram.org/bots#botfather), получите токен и вставьте его в переменную `TOKEN` в коде.

## Запуск

1. Убедитесь, что в коде указан ваш токен Telegram-бота:
    ```python
    TOKEN = "ваш-токен-бота"
    ```

2. Запустите бота:
    ```bash
    python main.py
    ```

3. После запуска бота в консоли появится сообщение:
    ```
    Бот запущен. Нажмите Ctrl+C для остановки.
    ```

4. В Telegram отправьте сообщение вашему боту и начните взаимодействие.

## Использование

- **/start**: Запуск бота. Приветственное сообщение.
- **Поиск iPhone**: Отправьте сообщение в формате `Поиск: <модель>`. Пример: `Поиск: iPhone 14`.
- **/order**: Оформление заказа.
- **/status**: Проверка статуса текущего заказа.
- **/cancel**: Отмена текущего заказа.

## Пример работы

1. Пользователь отправляет команду `/start`. Бот отвечает:
    ```
    Добро пожаловать в маркетплейс айфонов! Введите запрос, например: "Поиск: iPhone 14".
    ```

2. Пользователь отправляет сообщение: `Поиск: iPhone 14`. Бот отвечает:
    ```
    Найдены модели: iPhone 14 Pro, iPhone 14 Pro Max.
    ```

3. Пользователь отправляет команду `/order`. Бот отвечает:
    ```
    Ваш заказ оформлен.
    ```

4. Пользователь отправляет команду `/status`. Бот отвечает:
    ```
    Статус: Оформлен. Модель: iPhone 14 Pro Max. Дата: 2023-12-22 14:30:00.
    ```

5. Пользователь отправляет команду `/cancel`. Бот отвечает:
    ```
    Ваш заказ был отменен.
    ```

## Технические детали

- Бот разработан с использованием библиотеки **python-telegram-bot**.
- Асинхронное программирование реализовано с использованием модуля **asyncio**.
- Для работы с существующими циклами событий используется библиотека **nest_asyncio**.

## Требования

- Python 3.8 или выше
- Telegram Bot API токен

## Устранение ошибок

1. **RuntimeError: Cannot close a running event loop**  
   Убедитесь, что библиотека `nest_asyncio` установлена и применяется в начале скрипта:
   ```python
   import nest_asyncio
   nest_asyncio.apply()
