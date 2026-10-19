# Backend Basics

Учебный проект для знакомства со структурой Python-проекта.

Проект показывает минимальную структуру backend-кода: модель данных, сервисный слой, ожидаемые ошибки, логирование и отдельную точку запуска.

## Требования

- Python 3.12
- Git

## Установка

```bash
git clone <url-репозитория>
cd backend-basics
python3.12 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

На Windows окружение активируется командой `.venv\Scripts\activate`.

## Запуск

```bash
python main.py
```

Ожидаемый результат:

```text
INFO:tasks:Created task
Task(id=1, title='Подготовить README', description='Добавить инструкцию запуска проекта', due_date=datetime.date(2027, 6, 30))
```

## Структура проекта

```text
backend-basics/
├── src/
│   ├── __init__.py      # Python-пакет
│   ├── exceptions.py    # ожидаемые ошибки: TaskNotFoundError
│   ├── logger.py        # настройка логирования
│   ├── models.py        # модель данных Task (dataclass)
│   └── services.py      # бизнес-логика: create_task(), get_task()
├── .gitignore
├── main.py              # точка запуска сценария
├── README.md
└── requirements.txt
```

Задачи хранятся в словаре `dict[int, Task]`, поэтому поиск по `id` выполняется в среднем за O(1).

## Проверка кода

```bash
ruff check .
ruff format .
```
