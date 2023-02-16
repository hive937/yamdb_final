![example event parameter](https://github.com/hive937/yamdb_final/actions/workflows/yamdb_workflow.yml/badge.svg?event=push)
# **Проект Infra_sp2**
## **Описание**
Проект Infra_sp2 позволяет упаковать и запустить ранее созданный проект api_yamdb через создание образа и упаковку его в контейнер.
## **Как запустить проект**
Клонировать репозиторий и перейти в него в командной строке:
```
git clone https://github.com/hive937/infra_sp2
```
```
cd infra_sp2/infra
```
Выполнить команду для запуска контейнера
```
docker-compose up -d --build
```
## **Заполнение базы данными**
Для того, чтобы заполнить базу данными, необходимо выполнить следующие команды в командной строке, находясь в той же директории, что и при запуске:
Сделать миграции:
```
docker-compose exec web python manage.py migrate
```
Создать суперпользователя:
```
docker-compose exec web python manage.py createsuperuser
```
Собрать статику:
```
docker-compose exec web python manage.py collectstatic --no-input
```
## **Наполнение env-файла**
DB_ENGINE=django.db.backends.postgresql # указываем, что работаем с postgresql
DB_NAME=postgres # имя базы данных
POSTGRES_USER=postgres # логин для подключения к базе данных
POSTGRES_PASSWORD=postgres # пароль для подключения к БД
DB_HOST=db # название сервиса (контейнера)
DB_PORT=5432 # порт для подключения к БД 
SECRET_KEY= # секретный токен
### Технологии
- Python 3.9
- Django 2.2.16
- Django Rest Framework 3.12.4
- Docker 23.0.0
### Авторы
- Павел Вервейн | [hive937](https://github.com/hive937)
