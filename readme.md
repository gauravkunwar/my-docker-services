# Docker Services Setup

This repository contains a `docker-compose.yml` file to set up various self-hosted services using Docker and Docker Compose.

## 📌 Services Included

- **Audiobookshelf** - Self-hosted audiobook and podcast server.
- **File Browser** - Web-based file manager.
- **FreshRSS** - Self-hosted RSS feed aggregator.
- **Homepage** - Self-hosted dashboard for organizing services.
- **Jellyfin** - Media streaming server.
- **Kavita** - Self-hosted manga, comic, and book server.
- **Linkwarden** - Self-hosted bookmark manager.
- **Memos** - Self-hosted note-taking application.
- **Navidrome** - Music streaming server.
- **Nginx Proxy Manager** - Reverse proxy with SSL support.
- **Paperless-NGX** - Document management system.
- **Portainer** - Web UI for managing Docker containers.
- **Seafile** - Self-hosted file synchronization service.
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

You need to create an `.env` file to store environment variables. An example `.env.example` is provided.
Modify it as needed.

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

Examples:

| Service             | URL                      |
| ------------------- | ------------------------ |
| Audiobookshelf      | `http://localhost:13378` |
| File Browser        | `http://localhost:5050`  |
| FreshRSS            | `http://localhost:4065`  |
| Homepage            | `http://localhost:3000`  |
| Jellyfin            | `http://localhost:8096`  |
| Kavita              | `http://localhost:5000`  |
| Linkwarden          | `http://localhost:3160`  |
| Memos               | `http://localhost:5230`  |
| Navidrome           | `http://localhost:4533`  |
| Nginx Proxy Manager | `http://localhost:81`    |
| Paperless-NGX       | `http://localhost:5250`  |
| Portainer           | `http://localhost:9000`  |
| Seafile             | `http://localhost:8080`  |
| Syncthing           | `http://localhost:8384`  |
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
