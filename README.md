# YaMDb API


## Описание

Учебный проект создания API для базы данных произведений с отзывами и комментариями. 

Позволяет делать запросы к ресурсам БД с любого устройства.

Проект упакован в Docker контейнеры.

Образ на DockerHub: julka3561/api_yamdb:v1.0

## Шаблон заполнения .env файла

DB_ENGINE=*<тип БД>*

DB_NAME=*<имя базы данных>*

POSTGRES_USER=*<логин для подключения к базе данных>*

POSTGRES_PASSWORD=*<пароль для подключения к БД>*

DB_HOST=*<название сервиса (контейнера)>*

DB_PORT=*<порт для подключения к БД>*

## Запуск приложения в контейнерах

Клонировать репозиторий и перейти в папку infra в командной строке:
```
git clone https://github.com/julka3561/infra_sp2.git
```

```
cd infra
```

Запустить сборку контейнеров docker-compose:

```
docker-compose up -d
```
Провести миграции: 

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

## Заполнение базы данными

```
docker-compose exec web python manage.py loaddata fixtures.json 
```
## Об авторе
Юля & Яндекс.Практикум

Copyright (c) 2022, Julia Vasileva

All rights reserved.