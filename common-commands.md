# Docker Commands

## Common Docker Commands

- **Start all services defined in the `docker-compose.yml` file in the background**
  ```bash
  docker compose up -d
  ```

- **List all running containers**
  ```bash
  docker ps
  ```

- **List all containers (running and stopped)**
  ```bash
  docker ps -a
  ```

- **List all Docker images**
  ```bash
  docker images
  ```

- **Remove a stopped container**
  ```bash
  docker rm <container_id_or_name>
  ```

- **Remove an image**
  ```bash
  docker rmi <image_name>
  ```

- **Stop all running containers**
  ```bash
  docker stop $(docker ps -q)
  ```

- **Restart a stopped container**
  ```bash
  docker start <container_id_or_name>
  ```

- **Restart all running containers**
  ```bash
  docker restart $(docker ps -q)
  ```

- **Remove all stopped containers**
  ```bash
  docker rm $(docker ps -a -q)
  ```

- **Remove all dangling (unused) images**
  ```bash
  docker image prune
  ```

- **Remove all unreferenced images (not just dangling ones)**
  ```bash
  docker image prune -a
  ```

- **Remove all unused Docker volumes**
  ```bash
  docker volume prune
  ```

- **Remove all unused Docker networks**
  ```bash
  docker network prune
  ```

- **Stop and remove containers, images, volumes, and networks defined in the `docker-compose.yml` file**
  ```bash
  docker compose down
  ```

## Docker Housekeeping Commands

- **Pull the latest versions of all Docker images specified in `docker-compose.yml` file**
  ```bash
  docker compose pull
  ```

- **Start the containers as specified in the `docker-compose.yml` file in detached mode**
  ```bash
  docker compose up -d
  ```

- **Perform a system-wide cleanup in Docker**
 
  *This removes unused data, including stopped containers, unused networks, and all unreferenced images (not just dangling ones). The `--volumes` flag also removes unused volumes, which might lead to data loss if important volumes are not actively being used.*
  ```bash
  docker system prune -a --volumes
  
