# 🚀 FastAPI Business Management Backend

![FastAPI](https://img.shields.io/badge/FastAPI-005571?style=for-the-badge&logo=fastapi)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-316192?style=for-the-badge&logo=postgresql&logoColor=white)
![SQLAlchemy](https://img.shields.io/badge/SQLAlchemy-D71F00?style=for-the-badge&logo=sqlalchemy&logoColor=white)

Современный и быстрый REST API для управления внутренней конфигурацией бизнеса: сотрудниками, услугами и настройками организации.

---

## 🛠 Основной стек технологий
* **Python 3.10+**
* **FastAPI** — современный и быстрый фреймворк для создания API.
* **SQLAlchemy 2.0** — мощная ORM для работы с базой данных.
* **PostgreSQL** — основная реляционная база данных.
* **Pydantic** — строгая валидация данных и схем.
* **Bcrypt** — надежное хеширование паролей пользователей.

---

## 📂 Структура проекта

| Файл | Описание |
| :--- | :--- |
| `database.py` | Настройка подключения к БД, движок SQLAlchemy и генератор сессий `get_db`. |
| `models.py` | Описание таблиц базы данных (Organizations, Users, Services) через SQLAlchemy. |
| `schemas.py` | Pydantic-модели для валидации данных в запросах и ответах. |
| `main.py` | Основная логика API, маршруты (endpoints) и обработка бизнес-логики. |
| `requirements.txt` | Список всех необходимых библиотек и зависимостей. |

---

## ⚙️ Как запустить проект

### 1. Подготовка базы данных
Убедитесь, что у вас установлен **PostgreSQL**. Создайте новую базу данных:
```sql
CREATE DATABASE company_db;

```
Примечание: Если ваши данные доступа отличаются от стандартных (postgres:1234), обновите строку DATABASE_URL в файле database.py.

### 2. Установка окружения
Клонируйте репозиторий и установите зависимости:

# Создание виртуального окружения
python -m venv venv

# Активация (Windows)
venv\Scripts\activate

# Активация (Linux/macOS)
source venv/bin/activate

# Установка библиотек
pip install -r requirements.txt

### 3. Запуск сервера
Запустите приложение с помощью uvicorn:
uvicorn main:app --reload

После запуска сервер будет доступен по адресу: http://127.0.0.1:8000

## 📑 Документация API
FastAPI автоматически генерирует интерактивную документацию, где можно протестировать каждый запрос:

Swagger UI: http://127.0.0.1:8000/docs

ReDoc: http://127.0.0.1:8000/redoc

## ⚡ Основные возможности (Endpoints)
#### 👥 Сотрудники (POST /config/staff):

Наем новых сотрудников.

Автоматическое хеширование паролей через bcrypt.

Проверка существования организации и уникальности Email.

🛠 Услуги (PUT /config/services):

Настройка «меню» услуг.

Установка цен, длительности и описания.

🏢 Организация (PATCH /config/organization):

Гибкое обновление настроек бизнеса.

Смена времени работы, логотипа или статуса уведомлений.
