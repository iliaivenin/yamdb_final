# yamdb_final
## Развёрнутый и запущенный проект можно посмотреть по адресу http://178.154.219.144/api/v1
![yamdb workflow](https://github.com/iliaivenin/yamdb_final/actions/workflows/yamdb_workflow.yaml/badge.svg)


# API YaMDb
Учебный проект Яндекс.Практикум, выполнил Илья Ивенин.
Проект YaMDb собирает отзывы (Review) пользователей на произведения (Titles). Произведения делятся на категории: «Книги», «Фильмы», «Музыка». Список категорий (Category) может быть расширен администратором.
В каждой категории есть произведения: книги, фильмы или музыка.
Произведению может быть присвоен жанр (Genre) из списка предустановленных. Новые жанры может создавать только администратор.
Пользователи оставляют к произведениям текстовые отзывы (Review) и ставят произведению оценку в диапазоне от одного до десяти (целое число); из пользовательских оценок формируется усреднённая оценка произведения — рейтинг (целое число). На одно произведение пользователь может оставить только один отзыв.

## Для запуска проекта на локальном компьютере необходимо сделать следующее:
1. Установить Docker
2. Клонировать репозиторий, перейти в папку проекта:
```
git clone https://github.com/iliaivenin/yamdb_final
cd yamdb_final
```
3. В корне проекта создать файл .env:
```
DB_ENGINE=django.db.backends.postgresql
DB_NAME=postgres
POSTGRES_USER=<имя пользователя>
POSTGRES_PASSWORD=<пароль>
DB_HOST=db
DB_PORT=5432
```
4. Запустить проект, создать и применить миграции, собрать статику:
```
docker-compose up -d --build
docker-compose exec web python manage.py makemigrations --noinput
docker-compose exec web python manage.py migrate --noinput
docker-compose exec web python manage.py collectstatic --no-input
```


## Документация и админка
Документация API находится по адресу:
```
127.0.0.1/redoc
```
Панель администратора:
```
127.0.0.1/admin
```