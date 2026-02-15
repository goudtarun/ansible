# WordPress + MySQL using Docker Compose

## Project Overview

This project demonstrates how to deploy a multi-container WordPress application using Docker Compose.

The setup includes:

- WordPress (Web Application)
- MySQL (Database)
- Docker Compose (Container Orchestration)

This architecture simulates a real-world production environment where application and database services run in separate containers and communicate over an isolated Docker network.

---

## Technologies Used

- Docker
- Docker Compose
- WordPress (Official Image)
- MySQL 8 (Official Image)

---

## Architecture

```
Browser
│
▼
Host Port 80
│
▼
WordPress Container
│
▼
MySQL Container
```


Docker Compose automatically:

- Creates a bridge network
- Enables internal DNS resolution
- Allows WordPress to connect to MySQL using service name

---
### Services Configuration

### 1️⃣ WordPress Service

- Uses official `wordpress` image
- Exposes port 80
- Connects to MySQL using environment variables
- Persists website data using Docker volume

### 2️⃣ MySQL Service

- Uses official `mysql:8.0` image
- Stores database data in Docker volume
- Configured using environment variables

---

## Environment Variables Used

### WordPress

- `WORDPRESS_DB_HOST`
- `WORDPRESS_DB_USER`
- `WORDPRESS_DB_PASSWORD`
- `WORDPRESS_DB_NAME`

### MySQL

- `MYSQL_ROOT_PASSWORD`
- `MYSQL_DATABASE`

---

## How to Run the Project

### Navigate to the directory

Start Containers
```
docker compose up -d
```

### Access WordPress

If running locally:
```
http://localhost
```
If running on EC2:
```
http://<EC2-Public-IP>
Make sure port 80 is allowed in your EC2 Security Group.
```

Stop the Application
```
docker compose down
```

Author
Tarun Goud
DevOps Learner | Docker & Cloud Enthusiast


---





