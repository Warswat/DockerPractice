Создаём Image 
docker build . --tag=crud:v1

Создаём контейнер
docker run -d -p 8000:8000 --name CRUD crud:v1

Миграция для базы данных
winpty docker exec -it CRUD python manage.py migrate

Теперь по адресу http://localhost:8000/ доступны страницы admin и api/v1

Для проверки отправим запрос из requests-examples.http

POST {{baseUrl}}/products/
Content-Type: application/json

{
  "title": "Помидор",
  "description": "Лучшие помидоры на рынке"
}

После этого на странице http://localhost:8000/api/v1/products/ появилась новая запись
