# Production Docker Deployment

A professional-grade containerized deployment stack designed for scalability, security, and reliability. This project provides a blueprint for deploying Node.js applications with a PostgreSQL database and Nginx reverse proxy.

## 🚀 Features
- **Nginx Reverse Proxy**: Pre-configured with secure headers, proxy buffering, and health check endpoints.
- **Node.js (Express)**: Production-ready application logic with PostgreSQL integration.
- **PostgreSQL 15**: Hardened database configuration with persistent volume mapping and automated initialization.
- **Operational Hardening**: 
  - **Health Monitoring**: Self-healing containers using Docker healthchecks.
  - **Log Rotation**: Automated log cleanup to prevent disk overflow.
  - **Resource Management**: Strict CPU and memory limits per service.
- **Network Isolation**: Dedicated bridge network for internal service communication.

## 🛠️ Prerequisites
- Docker (v20.10+)
- Docker Compose (v2.0+)

## ⚙️ Configuration
1. **Clone the repository**:
   ```bash
   git clone https://github.com/ihkokil/docker-deployment.git
   cd docker-deployment
   ```

2. **Environment Setup**:
   Copy the example environment file and update your credentials:
   ```bash
   cp env.example .env
   ```

3. **Database Initialization**:
   The `init.sql` script runs automatically on the first container startup to seed the database.

## 📦 Deployment
Deploy the entire stack in detached mode:
```bash
docker-compose up -d --build
```

## 📊 Operational Commands
- **Check Status**: `docker-compose ps`
- **View Logs**: `docker-compose logs -f`
- **Stop Stack**: `docker-compose down`
- **Database Shell**: `docker exec -it postgres_db psql -U postgres -d app_db`

## 🛡️ Security
- Non-root user execution inside containers (recommended for prod).
- Resource throttling to prevent noisy neighbor issues.
- Secure Nginx headers (HSTS, CSP, X-Frame-Options).

## 👤 Author
**Md. Iqbal Haider Khan**
- GitHub: [@ihkokil](https://github.com/ihkokil)
- Email: ihkokil@gmail.com

---
*This repository is maintained for production-grade deployment demonstrations.*
