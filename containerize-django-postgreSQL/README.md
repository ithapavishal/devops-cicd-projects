# containerize-django-postgreSQL

README.md for GitHub repo documenting the Django + PostgreSQL containerization setup with Docker and Docker Compose.
Here’s a ready-to-use version:
# Employee CRUD App — Django + PostgreSQL + Docker Compose

This project demonstrates how to **containerize a Django application with PostgreSQL** using **Docker** and **Docker Compose**.  
It includes database persistence, environment variable configuration, and an entrypoint script to handle migrations automatically.

---

## 🚀 Features
- Django 5.x application with PostgreSQL database
- Containerized using Docker & Docker Compose
- Environment variables managed via `.env`
- Automatic migrations on container startup
- Data persistence with Docker volumes

---

## 📂 Project Structure

employee-crud/
├── employee/ # Django app
├── config/ # Django project settings
├── requirements.txt # Python dependencies
├── Dockerfile # Build Django image
├── docker-compose.yml # Define services (Django + PostgreSQL)
├── entrypoint.sh # Run migrations and start server
├── .env # Environment variables
└── README.md # Documentation

---

## ⚙️ Prerequisites
- [Docker](https://docs.docker.com/get-docker/) install
- [Docker Compose](https://docs.docker.com/compose/) install

---

## 🔑 Environment Variables

Create a **`.env`** file in the project root:

# PostgreSQL configuration
DB_NAME=employeecrud_db
DB_USER=postgres
DB_PASSWORD=your_password_here
DB_HOST=postgres_db
DB_PORT=5432

# Django development server ports
DJANGO_LOCAL_PORT=8000
DJANGO_DOCKER_PORT=8000


🐳 Docker Setup
1. Build and start containers
docker-compose up --build

3. Run in background (detached mode)
docker-compose up -d

5. Check running containers
docker ps

🗄️ Database Persistence
PostgreSQL data is stored in a named volume (pg_db_vol)
This ensures data is not lost when containers are stopped or removed

▶️ Accessing the App
Open in browser: 192.168.56.xx:8000

Or using container IP (example):
curl http://192.168.56.xx:8000/
