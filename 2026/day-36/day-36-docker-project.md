# Day 36 – Docker Project: Dockerize a Full Application

## Task

# Notes Manager

A simple Notes Manager web application built with **Python Flask** and **PostgreSQL**.

## Features

- Add Notes
- View Notes
- Edit Notes
- Delete Notes
- Bootstrap 5 Responsive UI
- PostgreSQL Database
- Dockerized using Docker Compose

---

## Tech Stack

- Python Flask
- Flask-SQLAlchemy
- PostgreSQL
- Docker
- Docker Compose

---

## Project Structure

```
notes-manager/
├── app.py
├── Dockerfile
├── docker-compose.yml
├── .env
├── requirements.txt
├── templates/
├── static/
└── README.md
```

---

## Environment Variables

Create a `.env` file with the following values:

```env
POSTGRES_DB=notesdb
POSTGRES_USER=notesuser
POSTGRES_PASSWORD=notespassword

DB_HOST=postgres
DB_PORT=5432
```

---

## Build and Run

Clone the repository:

```bash
git clone <repository-url>
cd notes-manager
```

Start the application:

```bash
docker compose up --build
```

Or run in detached mode:

```bash
docker compose up -d --build
```

---

## Access the Application

```
http://localhost:5000
```

Or if running on an EC2 instance:

```
http://<EC2-PUBLIC-IP>:5000
```

---

## Stop the Application

```bash
docker compose down
```

---

## Docker Image

```
docker pull yourusername/notes-manager:latest
```

