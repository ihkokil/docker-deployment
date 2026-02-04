# Production Docker Deployment

This repository demonstrates a production-grade containerized deployment stack using Node.js, PostgreSQL, and Nginx.

## Architecture
- **Application**: Node.js (Express)
- **Database**: PostgreSQL
- **Proxy**: Nginx (Reverse Proxy)
- **Orchestration**: Docker Compose

## Getting Started
1. Clone the repository
2. Configure environment variables
3. Run `docker-compose up -d`

## Production Notes
- **Log Rotation**: Configured to prevent disk exhaustion (max 10MB, 3 files).
- **Resource Limits**: CPU and memory capped to ensure system stability.
- **Health Checks**: Automated monitoring for self-healing (auto-restart on failure).
- **Security**: Nginx configured with hardened security headers and proxy buffering.
- **Database**: Persistent volumes used for data durability across container restarts.
