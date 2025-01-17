# Асинхронные запросы

В этом упражнении вы будете использовать SQLAlchemy для выполнения асинхронных запросов. Ваша задача — извлечь все фильмы из базы данных с использованием асинхронных операций. Для этого вам предстоит использовать асинхронный движок и сессии SQLAlchemy.

## Описание таблиц

Есть две таблицы: `directors` и `movies`. Таблица `directors` хранит информацию о режиссёрах, а `movies` — о фильмах. Каждая запись в таблице `movies` связана с одной записью в таблице `directors`, что представляет собой отношение «один ко многим». Модели описаны в файле *models.py*.

### Таблица `directors`

- `id` — идентификатор режиссёра, первичный ключ;
- `name` — имя режиссёра.

### Таблица `movies`

- `id` — идентификатор фильма, первичный ключ;
- `title` — название фильма;
- `director_id` — внешний ключ, ссылается на `directors.id`;
- `release_date` — дата выпуска фильма;
- `duration` — длительность фильма в минутах;
- `genre` — жанр фильма;
- `rating` — рейтинг фильма.

## src/solution.py

Ваша задача — написать асинхронную функцию `get_all_movies(session)`, которая возвращает список всех фильмов в базе данных. Каждый фильм должен быть представлен в виде строки формата: *The Shawshank Redemption by Frank Darabont, released on 1994-09-23, duration: 142 min, genre: Drama, rating: 9.3*.

Вам нужно настроить асинхронный движок и сессию SQLAlchemy, а также использовать асинхронные методы для выполнения запросов. Используйте жадную загрузку для получения информации о режиссёре каждого фильма

## .env

В URL-адрес подключения к базе данных добавьте `asyncpg` в диалектную часть.