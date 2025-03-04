# n8n with Traefik Setup

This repository provides a Docker-based setup to deploy n8n with pre-installed Traefik as a reverse proxy for secure and scalable workflow automation.

## Features
- **n8n**: Open-source workflow automation tool
- **Traefik**: Reverse proxy for SSL termination and load balancing
- **Docker Compose**: Easy containerized deployment
- **Let's Encrypt**: Automated SSL certificates

## Prerequisites
Ensure you have the following installed:
- Docker
- Docker Compose

## Installation
1. Clone this repository:
   ```sh
   git clone https://github.com/bizprat/n8n.git
   cd n8n
   ```

2. Create an `.env` file and configure the necessary environment variables:
   ```env
   DOMAIN_NAME=yourdomain.com
   SUBDOMAIN=n8n
   GENERIC_TIMEZONE=UTC
   SSL_EMAIL=example@example.com
   ```

3. Start the services:
   ```sh
   docker-compose up -d
   ```

## Configuration
- The `docker-compose.yml` file includes necessary configurations for Traefik and n8n.
- Ensure `traefik_data` and `n8n_data` volumes exist before running.
- Modify `WEBHOOK_URL` in the `environment` section for proper webhook functionality.

## Accessing n8n
Once the setup is running, access n8n at:
```
https://n8n.yourdomain.com
```

## Troubleshooting
- Check Traefik logs:
  ```sh
  docker logs traefik --follow
  ```
- Verify n8n logs:
  ```sh
  docker logs n8n-n8n-1 --follow
  ```
- Ensure n8n is correctly connected to the Traefik network:
  ```sh
  docker network inspect traefik
  ```

## License
This project is licensed under the MIT License.

