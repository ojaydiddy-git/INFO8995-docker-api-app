# Dockerized Flask API with PostgreSQL

This project is a containerized web application that exposes a simple REST API for creating and retrieving user data. It uses **Flask** for the API server and **PostgreSQL** for the database, all managed through **Docker Compose**.

---

## 🚀 Features

- `POST /user`: Create a new user (first name, last name)
- `GET /user/<id>`: Retrieve user by ID
- Logs API activity inside the container
- Data persistence with Docker Volumes
- Secure database access with environment variables
- Orchestrated using Docker Compose
- Designed for scalability and security

---

## 📁 Project Structure

docker-assignment/
│
├── app/
│ ├── main.py # Flask API server
│ ├── requirements.txt # Python dependencies
│ ├── Dockerfile # Web app container
│
├── db/
│ └── init.sql # Initializes PostgreSQL user table
│
├── .env # DB credentials (excluded from Git)
├── docker-compose.yml # Compose file to run everything
├── .gitignore # Ensures .env is not tracked
└── README.md # This file


---

## 🛠️ Setup Instructions (Using GitHub Codespaces)

### 1. Open this project in GitHub Codespaces

- Click the green **“Code”** button
- Select **“Open with Codespaces”** → “New Codespace”

### 2. Run the application

```bash
docker-compose up --build

Access the API
Go to the Forwarded Ports tab

Open the public URL for port 5000

Creating a User
POST /user
Content-Type: application/json

{
  "first_name": "John",
  "last_name": "Doe"
}

Get a User

GET /user/1

Security Best Practices Applied
Docker container runs as a non-root user

Environment variables are managed in a .env file (excluded from Git)

Uses slim base images (python:3.11-slim)

Docker volumes used for DB persistence

Internal network isolation via Docker networks

Scaling

docker-compose up --scale web=3 --build
