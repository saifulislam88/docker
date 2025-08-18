#### ✅Docker Installation Steps on Ubuntu | Docker Community Edition `docker-ce` 
The full Docker Engine package installation (daemon, CLI, etc.)
```sh
sudo apt update
sudo apt install apt-transport-https ca-certificates curl software-properties-common
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
echo "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt update
sudo apt install docker-ce docker-ce-cli containerd.io
sudo systemctl start docker containerd
sudo systemctl enable docker containerd
sudo systemctl status docker containerd
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

### What is docker.io?

- This is the Docker package from the default Ubuntu/Debian APT repositories
- Usually maintained by Debian/Ubuntu maintainers
- Often lagging behind the official Docker versions
- Still works, but may not have latest features or bug fixes
- Quickly test Docker on a Debian/Ubuntu VM


#### ✅Docker Installation Steps on Ubuntu | Ubuntu/Debian package name `docker.io` 
The name of the Docker package from the OS repo (usually older)

```bash
# Install docker from Ubuntu repo
sudo apt install docker.io
```

## **Installing Docker on Windows Server 2022: A Step-by-Step Guide**



![image](https://github.com/user-attachments/assets/a33d97af-2ad3-4143-a1c9-841bc0a90212)




### Step 1: Install DockerMsftProvider Module

At first **Open PowerShell as an administrator**

```sh
powershell Start-Process powershell -Verb runAs
```

To kickstart the installation process, we need to install the DockerMsftProvider module. Execute the following command in **PowerShell**:

```sh
Install-Module DockerMsftProvider -Force
```
### Step 2: Download Docker Installation Script

Next, we’ll download the Docker installation script from the official Microsoft repository. **Run the following command in PowerShell:**

```sh
Invoke-WebRequest -UseBasicParsing "https://raw.githubusercontent.com/microsoft/Windows-Containers/Main/helpful_tools/Install-DockerCE/install-docker-ce.ps1" -o install-docker-ce.ps1
```

### Step 3: Execute the Installation Script

Now that we have the installation script ready, let’s execute it to install Docker. Run the following command:

```sh
./install-docker-ce.ps1
```

### Step 4: Verify Docker Installation and Run Test `hello-world` Container

Once the installation process completes, it’s crucial to verify whether Docker has been installed successfully. You can do this by running the following command:

```sh
docker --version
docker run hello-world
```
