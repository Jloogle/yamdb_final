# Описание
Api v1 для проекта api_YaMDb<br>
Позволяет обращаться к базе и получать ответ в формате JSON
# Установка
1. Проверьте версию docker и убедитесь что он установлен, командой:
 ```
 docker -v 
 ```
2. Склонировать репозиторий командой:
 ```
 git clone git@github.com:Jloogle/infra_sp2.git
 ```
3. Перейти в папку с проектом, установить виртуальное окружение и активировать его:
```
 python3 -m venv venv
 ```
 ```
 source venv/bin/activate
 ```
4. Создайте файл .env внутри папки <u>infra</u>, в котором укажите переменные окружения:
   * SECRET_KEY
   * DB_ENGINE
   * DB_NAME
   * POSTGRES_USER
   * POSTGRES_PASSWORD
   * DB_HOST
   * DB_PORT
   
5. Перейдите в папку **infra** командой:
 ```
 cd infra/
 ```
6. Запустите процесс сборки контейнера командой:
 ```
docker-compose up -d
 ```
7. Запустите миграции внутри контейнера командами:
```
docker-compose exec web python manage.py makemigrations

docker-compose exec web python manage.py migrate
```
8. Создайте супер пользователя командой:
```
docker-compose exec web python manage.py createsuperuser
```
9. Загрузите статику командой:
```
docekr-compose exec web python manage.py collectstatic --no-input
```
10. По желанию загрузить готовую базу командой:
```
docekr-compose exec web python manage.py load_data_csv
```
11. Для остановки работы контейнеров используйте команду:
```
docker-compose stop
```
12. Для пересборки контейнеров используйте команду:
```
docker-compose up -d --build
```
13. Для доступа в админку перейдите по ссылке:
```
http://localhost/admin/
```
14. Подробное описание отправки запросов и получения ответов на них можно посмотреть на странице:
```
http://localhost/redoc/
```

Автор:<br>
Живов Игорь - https://github.com/Jloogle
