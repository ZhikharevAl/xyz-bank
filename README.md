
[![Ruff Linter](https://github.com/ZhikharevAl/TestNest/actions/workflows/ruff_check.yml/badge.svg)](https://github.com/ZhikharevAl/TestNest/actions/workflows/ruff_check.yml)
[![Run API Tests with Allure Report](https://github.com/ZhikharevAl/TestNest/actions/workflows/api-test.yml/badge.svg)](https://github.com/ZhikharevAl/TestNest/actions/workflows/api-test.yml)
[![Run Tests and Generate Allure Report](https://github.com/ZhikharevAl/TestNest/actions/workflows/auto-test.yml/badge.svg)](https://github.com/ZhikharevAl/TestNest/actions/workflows/auto-test.yml)
# Проект автоматизированного тестирования UI и API.

## Оглавление
- [Описание проекта](#описание-проекта)
- [Структура проекта](#структура-проекта)
- [Основные функции](#основные-функции)
- [Технологии и инструменты](#технологии-и-инструменты)
- [Настройка окружения](#настройка-окружения)
- [Запуск тестов](#запуск-тестов)
- [Структура отчетов](#структура-отчетов)
- [Особенности проекта](#особенности-проекта)

## Описание проекта

Данный проект представляет собой комплексный набор автоматизированных тестов для веб-приложения и API. Тесты охватывают как пользовательский интерфейс UI, так и программный интерфейс приложения API.

## Структура проекта

```
TestNest/
│
├── .github/               # Конфигурации GitHub
├── config/                # Конфигурационные файлы
├── data/                  # Модули для работы с данными
├── docs/                  # Документация
├── pages/                 # Page Object модели для UI
├── services/              # Сервисы для работы с API
├── tests/                 # Тестовые модули
│   ├── ui/                # UI тесты
│   └── api/               # API тесты
├── utils/                 # Вспомогательные утилиты
├── .gitignore
├── pyproject.toml         # Конфигурация Ruff
├── pytest.ini             # Конфигурация PyTest
├── README.md
└── requirements.txt       # Зависимости проекта
```

## Основные функции

### UI тестирование:
- Добавление нового клиента с валидными данными
- Сортировка списка клиентов
- Удаление клиентов

### API тестирование:
- CRUD операции для сущностей (создание, чтение, обновление, удаление)
- Получение списка всех сущностей

## Технологии и инструменты

- Python 3.10+
- Pytest
- Selenium WebDriver (для UI тестов)
- Requests (для API тестов)
- Allure для создания отчетов
- Faker для генерации тестовых данных
- GitHub Actions для непрерывной интеграции

## Настройка окружения

1. Убедитесь, что у вас установлен Python 3.10+
2. Склонируйте репозиторий:
   ```
   https://github.com/ZhikharevAl/TestNest.git
   cd TestNest
   ```
3. Создайте виртуальное окружение и активируйте его:
   ```
   python -m venv venv
   source venv/bin/activate  # Для Linux/Mac
   venv\Scripts\activate     # Для Windows
   ```
4. Установите зависимости:
   ```
   pip install -r requirements.txt
   ```

## Запуск тестов

Для запуска всех тестов:

```
pytest
```

Для запуска UI тестов:

```
pytest -m ui
```

Для запуска API тестов:

```
pytest -m api
```

Для генерации Allure-отчета:

```
pytest --alluredir=./allure-results
allure serve ./allure-results
```
![Screenshot 2024-09-30 025738](https://github.com/user-attachments/assets/58ee49fb-d1ca-42f1-948d-4ae276410437)

![Screenshot 2024-09-30 032136](https://github.com/user-attachments/assets/e8fd587f-3f0c-4d27-b32f-11d24fe129fc)


## Структура отчетов

Тесты используют фреймворк Allure для создания подробных отчетов. Каждый тест содержит:

- Описание теста
- Шаги выполнения теста
- Запросы и ответы API (для API тестов)
- Скриншоты (для UI тестов при падении)
- Уровень важности теста

## Особенности проекта

- Комплексное тестирование UI и API в рамках одного проекта
- Использование генераторов данных для создания тестовых данных
- Параметризация тестов для проверки различных сценариев
- Параллельный запуск тестов
- Автоматическое логирование запросов и ответов API
- Проверка корректности данных в ответах API и UI
- Документирование тест-кейсов в директории `docs/`
- Использование GitHub Actions для автоматического запуска тестов при push и pull request
