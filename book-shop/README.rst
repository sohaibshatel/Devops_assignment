Django Book Shop - Docker Deployment

This project is a Dockerized Django Book Shop application using PostgreSQL, Gunicorn, and Nginx.

Requirements
Docker
Docker Compose
Git
Setup

Clone the repository:

git clone https://github.com/sohaibshatel/Devops_assignment.git


Create the environment file:

cp .env.example .env

Start the containers:

docker-compose up --build

Run migrations:

docker-compose exec app python manage.py migrate

Create a superuser:

docker-compose exec app python manage.py createsuperuser
Access
Main App: http://localhost
Admin Panel: http://localhost/admin
Useful Commands
docker-compose up -d
docker-compose down
docker-compose logs -f
docker-compose exec app bash
Tech Stack
Django
PostgreSQL
Gunicorn
Nginx
Docker Compose

Date: May 2026
