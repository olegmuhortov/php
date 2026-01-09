REST API для управления задачами.

## Запуск

1. Клонировать репозиторий:

git clone https://github.com/yourusername/todo-api.git
cd todo-api

2. Установить зависимости:

composer install

3. Настроить среду:

cp .env.example .env
php artisan key:generate

4. Настроить базу данных:

touch database/database.sqlite

5. Запустить миграции:

php artisan migrate

6.Запустить сервер разработки:

php artisan serve

### Примеры запросов с использованием cURL:

1. Создание задачи:

curl -X POST http://localhost:8000/api/tasks \
  -H "Content-Type: application/json" \
  -H "Accept: application/json" \
  -d '{
    "title": "Новая задача",
    "description": "Описание новой задачи",
    "status": "pending"
  }'

2. Получение списка задач:

curl -X GET http://localhost:8000/api/tasks \
  -H "Accept: application/json"

3. Получение одной задачи:

curl -X GET http://localhost:8000/api/tasks/1 \
  -H "Accept: application/json"

4.Обновление задачи:

curl -X PUT http://localhost:8000/api/tasks/1 \
  -H "Content-Type: application/json" \
  -H "Accept: application/json" \
  -d '{
    "title": "Обновленный заголовок",
    "status": "completed"
  }'

5.Удаление задачи:

curl -X DELETE http://localhost:8000/api/tasks/1 \
  -H "Accept: application/json"
