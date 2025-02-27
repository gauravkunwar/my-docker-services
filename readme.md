# Docker Services Setup

This repository contains a `docker-compose.yml` file to set up various self-hosted services using Docker and Docker Compose.

## 📌 Services Included

- **Audiobookshelf** - Self-hosted audiobook and podcast server.
- **File Browser** - Web-based file manager.
- **FreshRSS** - Self-hosted RSS feed aggregator.
- **Guacamole** - Remote desktop gateway.
- **Home Assistant** - Smart home automation platform.
- **Homepage** - Self-hosted dashboard for organizing services.
- **IT Tools** - Collection of online networking tools.
- **Jellyfin** - Media streaming server.
- **Kavita** - Self-hosted manga, comic, and book server.
- **Linkwarden** - Self-hosted bookmark manager.
- **Memos** - Self-hosted note-taking application.
- **Navidrome** - Music streaming server.
- **Nginx Proxy Manager** - Reverse proxy with SSL support.
- **Paperless-NGX** - Document management system.
- **Portainer** - Web UI for managing Docker containers.
- **Seafile** - Self-hosted file synchronization service.
- **Stirling PDF** - Self-hosted PDF manipulation tool.
- **Syncthing** - File synchronization across devices.
- **Tailscale** - Secure VPN that makes remote access and networking simple using WireGuard encryption.
- **Transmission** - BitTorrent client for downloading torrents.
- **Vaultwarden** - Lightweight Bitwarden-compatible password manager.

## 🚀 Getting Started

### 1. Install Docker and Docker Compose

Ensure you have Docker and Docker Compose installed on your system:

```sh
sudo apt update && sudo apt install docker docker-compose -y
```

### 2. Clone this Repository

```sh
git clone https://github.com/gauravkunwar/my-docker-services.git
cd docker-setup
```

### 3. Create an `.env` File

You need to create an `.env` file to store environment variables. Here's an example:

```ini
# For multiple containers
HOME_DIR=/home/your-username
TIMEZONE=Your/Timezone

# For Tailscale
TAILSCALE_AUTHKEY=your_tailscale_authkey

# For Transmission
TRANSMISSION_USER=your_transmission_username
TRANSMISSION_PASS=your_transmission_password

# For Vaultwarden
VAULTWARDEN_DOMAIN=https://your.vaultwarden.domain
VAULTWARDEN_ADMIN_TOKEN=your_vaultwarden_admin_token

# For Paperless-ngx
PAPERLESS_URL=https://your.paperless.domain
PAPERLESS_ALLOWED_HOSTS=your.allowed.hosts,separated.by.commas
PAPERLESS_DBNAME=your_paperless_db_name
PAPERLESS_DBUSER=your_paperless_db_user
PAPERLESS_DBPASS=your_paperless_db_password
PAPERLESS_SECRET_KEY=your_paperless_secret_key

# For Postgres
POSTGRES_USER=your_postgres_user
POSTGRES_PASSWORD=your_postgres_password

# For yt-dlp
YT_DLP_SECRET=your_yt-dlp_secret
YT_DLP_USERNAME=your_yt-dlp_username
YT_DLP_PASSWORD=your_yt-dlp_password

# For WatchTower
TELEGRAM_BOT_TOKEN=your_telegram_bot_token
TELEGRAM_CHAT_ID=your_telegram_chat_id

# For Seafile
SEAFILE_HOSTNAME=https://your.seafile.domain
SEAFILE_ADMIN_EMAIL=your_seafile_admin@email
SEAFILE_ADMIN_PASSWORD=your_seafile_password
DB_PASSWORD=your_seafile_db_password_here
DB_NAME=your_seafile_db_name

# For Linkwarden
## Port configuration
LW_PORT=linkwarden_port_number
## Database configuration
LW_POSTGRES_USER=linkwarden_db_user
LW_POSTGRES_PASSWORD=linkwarden_db_password
LW_POSTGRES_DB=linkwarden_db_name
## NextAuth configuration
LW_NEXTAUTH_URL=http://localhost:linkwarden_port_number
LW_NEXTAUTH_SECRET=nextauth_secret
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

| Service             | URL                      |
| ------------------- | ------------------------ |
| Audiobookshelf      | `http://localhost:13378` |
| File Browser        | `http://localhost:5050`  |
| FreshRSS            | `http://localhost:4065`  |
| Guacamole           | `http://localhost:8348`  |
| Home Assistant      | `http://localhost:8123`  |
| Homepage            | `http://localhost:3000`  |
| IT Tools            | `http://localhost:8000`  |
| Jellyfin            | `http://localhost:8096`  |
| Kavita              | `http://localhost:5000`  |
| Linkwarden          | `http://localhost:3160`  |
| Memos               | `http://localhost:5230`  |
| Navidrome           | `http://localhost:4533`  |
| Nginx Proxy Manager | `http://localhost:81`    |
| Paperless-NGX       | `http://localhost:5250`  |
| Portainer           | `http://localhost:9000`  |
| Seafile             | `http://localhost:8080`  |
| Stirling PDF        | `http://localhost:8580`  |
| Syncthing           | `http://localhost:8384`  |
| Transmission        | `http://localhost:9091`  |
| Vaultwarden         | `http://localhost:8888`  |

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

Watchtower is configured to automatically update the containers daily at 2AM. However, you can manually update them with:

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
