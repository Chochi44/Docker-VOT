# Docker-VOT

Стартиране на  приложението

  1. Копиране на хранилището:
       git clone <repository-url>
       cd <repository-name>

  2. Стартиране на приложението с Docker compose:
       docker compose up -d

     Това ще:
     - Изгради Docker image за Flask приложението
     - Стартира PostgreSQL база данни
     - Свърже двата контейнера
     - Направи API досптъпно на http://localhost:5000

Endpoints

  1. Проверка на статуса:
       GET /health

  2. Създаване на потребител:
       curl -X POST -H "Content-Type: application/json" -d '{"name": "Ivan Ivanov", "email": "ivanov@example.com"}' http://localhost:5000/users

  3. Списък с всички потребители:
       GET /users

Спиране на приложението

  1. Спиране на приложението и запазване на данните:
        docker compose down
     
  2. Спиране на приложението и изтриване на данните:
       docker compose down -v

Структура на проекта

  - app.py - Flask приложение и модели
  - requirements.txt - Python зависимости
  - Dockerfile - инструкции за изграждане на Docker image
  - docker-compose.yml - конфигурация за Docker Compose
     
Забележки

  - PostgreSQL данните се съхраняват в Docker volume postgres_data
  - Базата данни е достъпна на порт 5432
  - API е достъпно на порт 5000
  - По подразбиране се използват следните credentials за базата данни:
      - Потребител: user
      - Парола: password
      - База данни: testdb
