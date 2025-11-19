# 🚀 Dockerized Node.js App

A simple production-ready Node.js application containerized with Docker.
### This project includes:

- Node.js application (src/)

- Dockerfile for containerizing the app

- docker-compose.yml for running multiple services (optional)

- .dockerignore to keep images small

## 📁 Folder Structure
Docker-node-app/
│
├── node_modules/        # Installed dependencies (ignored in Docker)
├── src/                 # Application source code
│   └── index.js         # Example Node server file
│
├── Dockerfile           # Docker image definition
├── docker-compose.yml   # For multi-service setup
├── .dockerignore        # Files to ignore in builds
├── package.json         # Node project metadata
└── package-lock.json

## ▶️ Run Application With Docker
### 1. Build Docker Image
```
docker build -t node-app .
```
### 2. Run the Container
```
docker run -p 3000:3000 node-app
```
Now open:

### 👉 http://localhost:3000

### ▶️ Run Using Docker Compose
```
docker-compose up --build
```
### Stops the app:
```
docker-compose down
```

## 🐛 Troubleshooting
1- Container exits immediately

2- Missing CMD in Dockerfile

3- Error in your Node.js entry file
Check logs:
```
docker logs <container-id>
```
4- Port already in use
```
sudo lsof -i :3000
kill -9 <PID>
```
5- Node modules inside container not installing

6- Check COPY package*.json before RUN npm install.

`### 🚀 Production Tips

1- Use multi-stage Docker builds to reduce image size

2- Add environment variables using docker-compose.yml

3- Use nginx reverse proxy in production
