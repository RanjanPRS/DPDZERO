
# Dockerized Microservices with Nginx Reverse Proxy

This project demonstrates a simple microservices architecture using **Docker**, **Docker Compose**, and **Nginx as a reverse proxy**.

It features two lightweight backend services — one in **Go** and another in **Python (Flask)** — running inside Docker containers and routed through Nginx. This is useful for demonstrating concepts like container orchestration, health checks, reverse proxies, and Docker networking.

## Project Structure

```bash
  DPDZERO/
├── docker-compose.yml
├── nginx/
│ ├── Dockerfile
│ └── nginx.conf
├── service_1/ # Golang microservice
│ ├── Dockerfile
│ └── main.go
├── service_2/ # Python Flask microservice
│ ├── Dockerfile
│ └── app.py
└── .gitignore

```

## Tech Stack

- 🐳 Docker
- 🧱 Docker Compose
- 🌐 Nginx (Reverse Proxy)
- 🐍 Python 3.11 (Flask API)
- 💻 Go 1.24 (Golang API)
- 🔍 Postman (API Testing)

##

```bash
| Route                    | Destination Container  | Port |
|--------------------------|------------------------|------|
| `/service1/ping`         | Go Service             | 8001 |
| `/service2/ping`         | Flask Service          | 8002 |
```
## Local Setup

```bash
git clone https://github.com/RanjanPRS/DPDZERO.git
cd DPDZERO
```

Install and run using Docker Compose
```bash
docker-compose up --build
```
This will:

- Build three images (Go, Flask, Nginx)

- Start containers only if services are healthy

- Route traffic via Nginx to respective apps

## Test Endpoints

Use Postman or your browser to hit:

- http://localhost:8080/service1/ping

- http://localhost:8080/service2/ping

- http://localhost:8080/service1/hello

- http://localhost:8080/service2/hello

Sample respone:

http://localhost:8080/service1/ping

```bash
{ "service": "1", "status": "ok" }
```
