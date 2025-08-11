#### Docker Compose 


1. Install Docker (if not already installed)

sudo apt-get update
sudo apt-get install -y docker.io

2. Download the Latest Docker Compose

sudo curl -L "https://github.com/docker/compose/releases/latest/download/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
sudo ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose
docker-compose --version

### 🚀Composer-Based Docker Images & Containers | Application Deployment

**`vim docker-compose.yaml`**

```sh
services:
  web:
    image: nginx:latest
    container_name: my_nginx_compose_default
    restart: unless-stopped
```

**OR**

```sh
services:
  web:
    image: nginx:latest
    container_name: my_nginx_compose_host
    network_mode: "host"  # Use the host network
    ports:
      - "8080:80"  # Maps port 8080 on the host to port 80 in the container
    restart: unless-stopped
```

`docker-compose down`\
`docker-compose up -d`\
`docker ps`

