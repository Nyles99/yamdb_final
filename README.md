![Cтатус workflow](https://github.com/TrofimovAleksey/yamdb_final/actions/workflows/yamdb_workflow.yml/badge.svg)

yamdb_final
example workflow

Проект YaMDb собирает отзывы пользователей на произведения. Произведения делятся на категории:«Книги», «Фильмы», «Музыка». Список категорий может быть расширен (например, можно добавить категорию «Изобразительное искусство» или «Ювелирка»). Настроика для приложения Continuous Integration и Continuous Deployment, реализация:

автоматический запуск тестов,
обновление образов на Docker Hub,
автоматический деплой на боевой сервер при пуше в главную ветку main.
Стек:

Django 3.2
django-extensions==3.2.1
Nginx
docker-compose
Клонировать репозиторий:
git clone ...
Добавить в клонированный репозиторий секреты (Settings/Secrets):
Переменная: USER, значение: <имя пользователя для подключения к серверу>
Переменная: HOST, значение: <публичный ip-адрес сервера>
Переменная: SSH, значение: <закрытый ssh-ключ для подключения к серверу>
Переменная: PASSPHRASE, значение: <пароль, если ssh-ключ защищён паролем>
Переменная: DB_ENGINE, значение: django.db.backends.postgresql
Переменная: DB_HOST, значение: db
Переменная: DB_NAME, значение: postgres
Переменная: DB_PORT, значение: 5432
Переменная: POSTGRES_USER, значение: postgres
Переменная: POSTGRES_PASSWORD, значение: postgres
Переменная: TELEGRAM_TO, значение: <токен Вашего телеграм-аккаунта>
Переменная: TELEGRAM_TOKEN, значение: <токен Вашего телеграм-бота>
В файле
/infra/nginx/default.conf
в строке 'server_name <ip-адрес>' указать публичный ip-адрес сервера

Скопировать на сервер файлы:
scp docker-compose.yaml <пользователь_сервера>@<ip-адрес сервера>:/home/<домашняя папка>
scp -r /nginx <пользователь_сервера>@<ip-адрес сервера>:/home/<домашняя папка>
На сервере оставить nginx и установить пакеты docker.io и docker-compose
84.252.143.165:82/admin

https://github.com/nyles99/yamdb_final
