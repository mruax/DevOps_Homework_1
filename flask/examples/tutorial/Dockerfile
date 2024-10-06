# Используем базовый образ Python
FROM python:3.9-slim
LABEL authors="mruax"

# Устанавливаем рабочую директорию
WORKDIR /app

# Копируем файл requirements.txt и устанавливаем зависимости
COPY requirements.txt requirements.txt
RUN pip install -r requirements.txt

# Копируем приложение в рабочую директорию
COPY . .

# Устанавливаем переменные окружения для Flask
ENV FLASK_APP=flaskr
ENV FLASK_ENV=development

# Инициализация базы данных
RUN flask --app flaskr init-db

# Запуск сервера
CMD ["flask", "--app", "flaskr", "run", "--host=0.0.0.0"]

# Открываем порт
EXPOSE 5000
