
![image](https://github.com/user-attachments/assets/a33d97af-2ad3-4143-a1c9-841bc0a90212)

## **Installing Docker on Windows Server 2022: A Step-by-Step Guide**


### Step 1: Install DockerMsftProvider Module

At first **Open PowerShell as an administrator**\

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
