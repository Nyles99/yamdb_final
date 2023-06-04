FROM python:3.7-slim

WORKDIR /app/

# Скопировать с локального компьютера файл зависимостей
# в директорию /app.
COPY . .

# Выполнить установку зависимостей внутри контейнера.
RUN pip3 install -r requirements.txt --no-cache-dir

# Выполнить запуск сервера разработки при старте контейнера.
CMD ["gunicorn", "api_yamdb.wsgi:application", "--bind", "0:8000" ]