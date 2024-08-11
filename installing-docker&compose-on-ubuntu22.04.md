## To install the latest version of Docker & Compose on Ubuntu 22.04

### Docker Installation

```sh
sudo apt-get update -y
sudo apt-get install -y apt-transport-https ca-certificates curl gnupg lsb-release
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

sudo apt-get update -y
sudo apt-get install -y docker-ce docker-ce-cli containerd.io
sudo systemctl enable docker && sudo systemctl start docker
sudo docker --version

# Optionally, add your user to the Docker group to run Docker commands without `sudo`
sudo usermod -aG docker $USER 
```
**`docker run -dit --name Rock nginx`**
**`docker ps `**


### Docker Compose

```sh
sudo curl -L "https://github.com/docker/compose/releases/latest/download/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose 
sudo chmod +x /usr/local/bin/docker-compose 
sudo ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose 
docker-compose --version
```

**`vim docker-compose.yaml`**

```sh
services:
  web:
    image: nginx:latest
    container_name: my_nginx_compose
    ports:
      - "8080:80"  # Maps port 8080 on the host to port 80 in the container
    restart: unless-stopped
```

**`docker-compose down`**
**`compose up -d`**
**`docker ps`**
