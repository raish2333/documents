# 🐳 Docker Installation & Basic Usage Guide (Ubuntu)

## 📦 Install Docker on Ubuntu

### 1. ✅ Check if `apt` is available
Make sure your system supports `apt` package manager (should be available on Ubuntu by default).

```bash
apt --version
```

### 2. 📥 Install Docker
```bash
sudo apt update
sudo apt install docker.io -y
```

### 3. 📚 Post-Installation Steps
Follow the official Docker post-install steps to manage Docker as a non-root user:

👉 [https://docs.docker.com/engine/install/linux-postinstall/](https://docs.docker.com/engine/install/linux-postinstall/)

---
### for run images in background

👉 docker run -d -p 3000:3000 --name front-end frontend

## Important Docker compose file for microservices
👉 sudo curl -SL https://github.com/docker/compose/releases/download/v2.36.2/docker-compose-linux-x86_64 -o /usr/local/bin/docker-compose
👉 sudo chmod +x /usr/local/bin/docker-compose
👉 Dcoker-compose up
👉 Docker-compose down

## remove all images
docker rmi -f $(docker images -q)
 
## 🧰 Image & Container Commands

| Task                    | Command                 | Description                     |
|-------------------------|-------------------------|---------------------------------|
| **Check version**       | `docker --version`      | Show Docker version             |
| **Login to Docker Hub** | `docker login`          | Authenticate to Docker registry |
| **Pull image**          | `docker pull nginx`     | Download image from Docker Hub  |
| **List images**         | `docker images`         | See all downloaded images       |
| **Remove image**        | `docker rmi <image_id>` | Delete an image                 |

---

## 🚀 Running Containers

| Task                        | Command                       | Description              |
|-----------------------------|-------------------------------|--------------------------|
| **Run container**           | `docker run hello-world`      | Test Docker installation |
| **Run with port**           | `docker run -p 8080:80 nginx` | Run with port mapping    |
| **Run with name**           | `docker run --name web nginx` | Assign a name            |
| **Run in background**       | `docker run -d nginx`         | Detached mode            |
| **List running containers** | `docker ps`                   | See active containers    |
| **List all containers**     | `docker ps -a`                | Include stopped ones     |
| **Stop a container**        | `docker stop <container_id>`  | Stop it                  |
| **Remove container**        | `docker rm <container_id>`    | Delete it                |

---

## 🛠️ Building Custom Images

| Task                   | Command                              | Description           |
|------------------------|--------------------------------------|-----------------------|
| **Build image**        | `docker build -t myapp .`            | Build from Dockerfile |
| **Tag image**          | `docker tag myapp username/myapp:v1` | Tag before pushing    |
| **Push to Docker Hub** | `docker push username/myapp:v1`      | Upload image          |

---

## 📁 Volumes & Networks

| Task               | Command                            | Description        |
|--------------------|------------------------------------|--------------------|
| **Create volume**  | `docker volume create myvol`       | Persistent storage |
| **Use volume**     | `docker run -v myvol:/data alpine` | Mount volume       |
| **Create network** | `docker network create mynet`      | Isolated network   |
| **Use network**    | `docker run --network mynet nginx` | Join network       |
