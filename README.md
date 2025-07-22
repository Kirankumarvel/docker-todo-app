# Docker Todo App

A full-stack todo application built with Docker containers, featuring a React frontend, Flask backend, and PostgreSQL database.

## Features

- Create, read, update, and delete todos
- Mark todos as complete
- Persistent data storage
- Containerized microservices architecture

## Technology Stack

- **Frontend**: React.js
- **Backend**: Flask (Python)
- **Database**: PostgreSQL
- **Containerization**: Docker with Docker Compose

## Prerequisites

Before you begin, ensure you have the following installed:

- Docker ([Installation Guide](https://docs.docker.com/get-docker/))
- Docker Compose ([Installation Guide](https://docs.docker.com/compose/install/))
- Git (optional)

## Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/Kirankumarvel/docker-todo-app.git
cd docker-todo-app
```

### 2. Build and Run the Application

```bash
docker-compose up --build
```

This command will:
- Build the Docker images for all services
- Start the containers
- Set up the database
- Launch the application

### 3. Access the Application

- **Frontend**: Open [http://localhost:3000](http://localhost:3000) in your browser
- **Backend API**: Accessible at [http://localhost:5000](http://localhost:5000)

## Project Structure

```
docker-todo-app/
├── backend/            # Flask API
│   ├── Dockerfile
│   ├── app.py          # Main application code
│   ├── requirements.txt
├── frontend/           # React application
│   ├── Dockerfile
│   ├── public/         # Static files
│   ├── src/            # React components
│   ├── package.json
├── docker-compose.yml  # Orchestration configuration
├── README.md           # This file
```

## Available Services

| Service   | Port  | Description                     |
|-----------|-------|---------------------------------|
| frontend  | 3000  | React application               |
| backend   | 5000  | Flask REST API                  |
| db        | 5432  | PostgreSQL database (internal)  |

## Development

### Environment Variables

The application uses the following environment variables:

- **Backend**:
  - `FLASK_ENV`: Set to "development" for debug mode
  - `SQLALCHEMY_DATABASE_URI`: Database connection string

- **Database**:
  - `POSTGRES_USER`: Database username
  - `POSTGRES_PASSWORD`: Database password
  - `POSTGRES_DB`: Database name

### Hot Reloading

The development setup includes volume mounts for both frontend and backend, enabling:
- Automatic React frontend reloading
- Flask backend reloading on code changes

### Common Commands

- Start the application:
  ```bash
  docker-compose up
  ```

- Start in detached mode:
  ```bash
  docker-compose up -d
  ```

- Stop the application:
  ```bash
  docker-compose down
  ```

- Stop and remove volumes (including database data):
  ```bash
  docker-compose down -v
  ```

- Rebuild containers:
  ```bash
  docker-compose up --build
  ```

- View running containers:
  ```bash
  docker-compose ps
  ```

- View logs:
  ```bash
  docker-compose logs
  ```

## Troubleshooting

### Database Issues

If you encounter database connection problems:
1. Stop the containers: `docker-compose down -v`
2. Remove the database volume: `docker volume rm docker-todo-app_postgres_data`
3. Restart: `docker-compose up --build`

### Port Conflicts

Ensure ports 3000 and 5000 are available on your system. You can modify these in the `docker-compose.yml` file if needed.

## License

This project is open-source and available under the [MIT License](LICENSE).

---

**Happy coding!** 🐳
```
