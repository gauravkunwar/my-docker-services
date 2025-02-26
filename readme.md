
# Docker Services Setup

This repository contains a `docker-compose.yml` file to set up various self-hosted services using Docker and Docker Compose.

## 📌 Services Included

- **Home Assistant** - Smart home automation platform.
- **Navidrome** - Music streaming server.
- **Linkwarden** - Self-hosted bookmark manager.
- **Nginx Proxy Manager** - Reverse proxy with SSL support.
- **Watchtower** - Automatic updates for Docker containers.
- **Tailscale** - Secure VPN for remote access.
- **Transmission** - BitTorrent client for downloading torrents.
- **Syncthing** - File synchronization across devices.
- **Jellyfin** - Media streaming server.
- **FreshRSS** - Self-hosted RSS feed aggregator.
- **Paperless-NGX** - Document management system.
- **Redis** - In-memory key-value store for caching.
- **PostgreSQL** - Database for Paperless-NGX & Linkwarden.

## 🚀 Getting Started

### 1. Install Docker and Docker Compose

Ensure you have Docker and Docker Compose installed on your system:

```sh
sudo apt update && sudo apt install docker docker-compose -y
```

### 2. Clone this Repository

```sh
git clone https://github.com/your-username/docker-setup.git
cd docker-setup
```

### 3. Create an `.env` File

You need to create an `.env` file to store environment variables. Here's an example:

```ini
HOME_DIR=/home/your-username
TIMEZONE=America/New_York

LW_POSTGRES_USER=linkwarden
LW_POSTGRES_PASSWORD=securepassword
LW_POSTGRES_DB=linkwarden

LW_NEXTAUTH_SECRET=your-secret-key
LW_PORT=3000

TELEGRAM_BOT_TOKEN=your-bot-token
TELEGRAM_CHAT_ID=your-chat-id

TAILSCALE_AUTHKEY=your-tailscale-auth-key

TRANSMISSION_USER=your-username
TRANSMISSION_PASS=your-password

PAPERLESS_URL=http://your-server-ip:5250
PAPERLESS_ALLOWED_HOSTS=your-server-ip
PAPERLESS_DBNAME=paperless
PAPERLESS_DBUSER=paperless
PAPERLESS_DBPASS=securepassword
PAPERLESS_SECRET_KEY=your-secret-key
```

### 4. Start the Containers

Run the following command to start all services:

```sh
docker-compose up -d
```

### 5. Verify Running Containers

Check if all containers are running:

```sh
docker ps
```

### 6. Access the Services

| Service              | URL                           |
|----------------------|-----------------------------|
| Home Assistant      | `http://localhost:8123`      |
| Navidrome           | `http://localhost:4533`      |
| Linkwarden         | `http://localhost:3000`      |
| Nginx Proxy Manager | `http://localhost:81`       |
| Transmission        | `http://localhost:9091`     |
| Syncthing          | `http://localhost:8384`      |
| Jellyfin           | `http://localhost:8096`      |
| FreshRSS           | `http://localhost:4065`      |
| Paperless-NGX      | `http://localhost:5250`      |

### 7. Stopping and Removing Containers

To stop the containers:

```sh
docker-compose down
```

To stop and remove all containers, volumes, and networks:

```sh
docker-compose down -v
```

## 🛠 Maintenance

### Update Containers

Watchtower is configured to automatically update the containers. However, you can manually update them with:

```sh
docker-compose pull
docker-compose up -d
```

### Check Logs

You can check logs for a specific container:

```sh
docker logs -f homeassistant
```

Or check logs for all containers:

```sh
docker-compose logs -f
```

## 🎯 Notes

- This setup assumes that your `$HOME_DIR` is correctly set in the `.env` file.
- Some services require additional configuration through their web UI after initial setup.
- Ensure that you change default passwords and secrets in your `.env` file before running the setup.

