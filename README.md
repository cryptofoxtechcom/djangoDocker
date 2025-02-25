# 🚀 Django Application with Docker Compose

This project sets up a Django application with Nginx and PostgreSQL using Docker Compose. It provides a lightweight and efficient development environment.

---

## 🛠️ Services Overview

### 🐍 **Django Application Service**
- **Base Image**: `python:3.9-slim` (lightweight Python environment)
- **Functionality**:
  - Mounts the Django application code into the container.
  - Installs dependencies and runs the Django development server on port `8000`.
  - Connects to the PostgreSQL database using environment variables.

### 🌐 **Nginx Service**
- **Base Image**: `nginx:alpine` (lightweight Nginx server)
- **Functionality**:
  - Exposes port `80` to serve the Django application.
  - Requires a custom `nginx.conf` file to proxy requests to the Django app.

### 🐘 **PostgreSQL Database Service**
- **Base Image**: `postgres:13-alpine` (lightweight PostgreSQL database)
- **Functionality**:
  - Persists database data in a Docker volume (`postgres_data`).
  - Configures the database name, user, and password via environment variables.

---

## 🌐 **Networks**
- All services are connected to a custom bridge network (`django_network`) for seamless communication.

---

## 💾 **Volumes**
- The `postgres_data` volume ensures that database data persists across container restarts.

---

## 🚦 **Steps to Use**

1. **After you clone the repository** you will find the necessary files.
2. **Ensure you have docker running** this allows you to run the compose file.
3. **Look at the settings.py file for configurations** update ALLOWED_HOSTS to match your ip.
4. **Run the following command** to start the services:
   ```bash
   docker-compose up -d
