#### ✅Installation Steps on Ubuntu

```sh
sudo apt update
sudo apt install apt-transport-https ca-certificates curl software-properties-common
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
echo "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt update
sudo apt install docker-ce
sudo systemctl start docker
sudo systemctl enable docker
sudo systemctl status docker
```
#### ✅Add User to Docker Group (Optional, to Run Without sudo)

```sh
sudo usermod -aG docker $USER
newgrp docker
```

#### ✅Run Your First Container using Docker Registry(Public Repo: https://hub.docker.com/)

```sh
docker --version
docker run hello-world
```

```sh
docker run -it -d -p 8080:80 --name web nginx:latest
docker run -it -d -p 80:80 --name web-nginx nginx
docker ps -a
```
