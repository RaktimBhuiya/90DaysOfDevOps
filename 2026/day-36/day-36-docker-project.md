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

## Final Project Structure

```text
notes-manager/
│
├── app.py
├── Dockerfile
├── docker-compose.yml
├── .dockerignore
├── .env
├── README.md
├── requirements.txt
│
├── templates/
│   ├── base.html
│   ├── index.html
│   ├── add_note.html
│   └── edit_note.html
│
└── static/
    └── style.css
```

## What the app does

Notes Manager is a simple web application built with Python Flask and PostgreSQL that allows users to manage their notes efficiently. Users can create new notes, view all saved notes, edit existing notes, and delete notes through an intuitive and responsive web interface. The application uses Flask-SQLAlchemy for database operations and is containerized using Docker and Docker Compose for easy deployment.

## How to run it with Docker Compose

## How to Run with Docker Compose

1. Clone the repository:

```bash
git clone <your-repository-url>
cd notes-manager
```

2. Create a `.env` file in the project root with the required environment variables:

```env
POSTGRES_DB=notesdb
POSTGRES_USER=notesuser
POSTGRES_PASSWORD=notespassword
DB_HOST=postgres
DB_PORT=5432
```

3. Build and start the application:

```bash
docker compose up --build
```

Or run it in detached mode:

```bash
docker compose up -d --build
```

4. Open your browser and access the application:

```
http://localhost:5000
```

If running on an AWS EC2 instance:

```
http://<EC2-PUBLIC-IP>:5000
```

5. To stop the application:

```bash
docker compose down
```

## Any environment variables needed

Create a `.env` file in the project root with the following variables:

```env
POSTGRES_DB=notesdb
POSTGRES_USER=notesuser
POSTGRES_PASSWORD=notespassword
DB_HOST=postgres
DB_PORT=5432
```

### Description

| Variable | Description |
|----------|-------------|
| `POSTGRES_DB` | Name of the PostgreSQL database. |
| `POSTGRES_USER` | PostgreSQL username used by the application. |
| `POSTGRES_PASSWORD` | Password for the PostgreSQL user. |
| `DB_HOST` | Hostname of the PostgreSQL service (Docker Compose service name). |
| `DB_PORT` | Port on which PostgreSQL is listening (default: `5432`). |