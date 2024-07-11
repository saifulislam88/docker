#**Docker Container Administrator | An Introduction & Principle Concept**

**DOCX by**
![image](https://github.com/saifulislam88/docker/assets/68442870/09012688-7671-4f50-8208-dedad3b66353)

- **Copyright © 2024 Md. Saiful Islam(mSI). All Rights Reserved**
- Reference : Internet & ChatBot

**Table of contents**
- [Technological Transformation](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#technological-transformation)
   - Bare Metal
   - Key Reasons for Transition
- [Virtualization](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#virtualization)
   - [KVM Virtualization](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#virtualization)
    - [KVM features](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#kvm-features)
   - [OS Virtualization](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#os-virtualization)
      - [User Space vs Kernel Space](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#user-space-vs-kernel-space)
      - [Container](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#container)
         - [More Defination](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#more-defination)
         - [Different Container or Container runtimes provider](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#different-container-or-container-runtimes-provider)
         - [What is Docker](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#docker)
          - [Docker Features](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#docker-features)
          - [Why We should use Docker Container](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#why-use-docker-container)
          - [Docker Architecture and Components](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#docker-architecture-and-components)
          - [Container Application Deployment lifecycle on Docker](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#container-application-deployment-lifecycle-on-docker)
            - [Install Docker: Set up Docker on your machine & Run your first container.](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#install-docker-set-up-docker-on-your-machine--run-your-first-container)
              - [Docker Installation Steps on Ubuntu](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#--installation-steps-on-ubuntu)
              - [Run your first container using Docker Registry(Public Repo: https://hub.docker.com/)](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#--run-your-first-container-using-docker-registrypublic-repo-httpshubdockercom)
              - [Explain basic Docker usage workflow](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#--explain-basic-docker-usage-workflow)
            - [Create a Dockerfile: Define your application's environment and dependencies.](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#create-a-dockerfile-define-your-applications-environment-and-dependencies)
              - [Writing a Dockerfile for a simple application | Set up a nodejs project](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#--writing-a-dockerfile-for-a-simple-application--set-up-a-nodejs-project)
              - [Create a file named app.js in your project directory and add the following code:](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#--create-a-file-named-appjs-in-your-project-directory-and-add-the-following-code)
              - [Run and Test Your Application: You should see the message Example app listening at http://localhost:3000](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#--run-and-test-your-application-you-should-see-the-message-example-app-listening-at-httplocalhost3000)
              - [Write a Dockerfile on Nodejs project](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#--write-a-dockerfile-on-nodejs-project) 
            - [Build an Image: Use the Dockerfile to build a Docker image & Run from local.](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#build-an-image-use-the-dockerfile-to-build-a-docker-image--run-from-local)
            - [Tag | Login | Push the Docker Image.](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#tag--login--push-the-docker-image)
            - [Pull and Run : Download the image from Docker Hub | Create and run a container from the Docker image.](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#pull-and-run---download-the-image-from-docker-hub-on-another-machine--create-and-run-a-container-from-the-docker-image)
            - [Manage Containers: Use Docker commands to manage the lifecycle of containers.](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#manage-containers-use-docker-commands-to-manage-the-lifecycle-of-containers)
            - [Deploy Updates: Rebuild, retag, push updates, and restart the container to deploy updates.](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#deploy-updates-rebuild-retag-push-updates-and-restart-the-container-to-deploy-updates)



            




### 🚀Technological Transformation

 - #### 🔥**Bare Metal**
   - Performance: Direct access to hardware, no virtualization overhead.
   - Control: Full control over the hardware and software stack.
   - Use Case: High-performance computing, gaming servers, financial trading systems.

<p align="right">
<img src="https://github.com/saifulislam88/docker/assets/68442870/401f1965-77cb-450a-b558-5ad80b1428ea" alt="Technological Transformation" width="800"/>
</p>

 - #### 🔥**Key Reasons for Transition:**
   - **Bare Metal to Virtualization:** To improve resource utilization, flexibility, and isolation while maintaining control over the hardware.
   - **Virtualization to Cloud:** To leverage scalability, cost efficiency, reduced maintenance, and global accessibility, enabling faster innovation and business agility.
   - **Example:** Instead of having ten servers each running at 10% capacity, virtualization can consolidate them into one or two servers running at 80-90% capacity.

### 🚀Virtualization

**Virtualization is software technology that separates physical infrastructures to create multiple virtual machine (VM) or virtual environments on a single server.**

This software technology of virtualization system is known as a virtual machine monitor (VMM) or virtual manager, which separates compute environments from the actual physical infrastructure–this makes it possible to run several operating systems on one computer at the same time. 
**A virtual machine monitor or VMM, also known as a hypervisor, is software that creates, runs and manage virtual machines (VMs).**

- **Resource Utilization:** Better utilization of physical hardware by running multiple VMs.
- **Isolation:** Strong isolation between applications.
- **Flexibility:** Easier to create, manage, and scale VMs.
- **Use Case:** Server consolidation, development and testing environments.


<p align="right">
<img src="https://github.com/saifulislam88/docker/assets/68442870/3c392818-aa43-4313-8893-72d83f1a5019" alt="Technological Transformation" width="800"/>
</p>

There are **two** main types of virtualization technology — 

   - **KVM Virtualization**
   - **OS Virtualization**

 #### 🔥KVM Virtualization

**KVM (Kernel-Based Virtual Machine) Is An Open-Source Virtualization Technology That Allows You To Run Multiple Virtual Machines (VMs) On A Linux/Windows Host**. A Kernel-based Virtual Machine (KVM) allows you to turn Linux or Windows Server into a hypervisor, allowing your operating system to produce multiple virtual machines and isolated virtual environments.

 - **Type 1 - hypervisor** is running on **bare-metal hardware**. Such hypervisors are VMWare ESXi, Linux KVM, Hyper-V
 - **Type 2 - hypervisor** is running inside **Host OS**. Such hypervisors are VMWare Workstation are Oracle VirtualBox

##### 📌KVM features
 - Security
 - Storage
 - Hardware support
 - Memory management
 - Live migration
 - Performance and scalability
 - Scheduling and resource control
 - Lower latency and higher prioritization

#### 🔥OS Virtualization

**একটি কার্নেলের ওপর একাধিক isolated ইউসার স্পেইসের অস্তিত্বকে অপারেটিং সিস্টেম লেভেল ভার্চুয়ালাইজেসন বলে.**
প্রতিটা ইউসার স্পেইসের রানটাইম এনভায়রনমেন্ট, ইউসার সেটিংস, ইত্যাদি ভিন্ন। আর একটা ইউসার স্পেইসের প্রসেস আরেকটা ইউসার স্পেইসে প্রবেশ করতে পারে না। মানে মেমোরি প্রটেকশন.

##### 📌**User Space vs Kernel Space**
অপারেটিং সিস্টেমে কিছু প্রসেস আছে যাদের সিস্টেম রিসোর্সগুলো (System Resource) সরাসরি অ্যাক্সেস করার প্রিভিলেজ (Privilege) থেকে থাকে। এই প্রসেসগুলো সাধারণত কার্নেল (Kernel) এবং ডিভাইস ড্রাইভার (Device Drivers) হয়ে থাকে। এসমস্ত প্রিভিলেজসম্পন্ন প্রসেসসমুহের মেমোরি প্রটেকশনের জন্যে ভার্চুয়াল মেমোরি স্পেইসের একাংশকে dedicate করে দেয়া হয় । এর কারনে ভার্চুয়াল মেমোরি দ্বিখণ্ডিত হয় । একটি খণ্ডে চলে কার্নেল আর ডিভাইস ড্রাইভারদের মত প্রিভিলেজ সম্পন্ন প্রসেসসমুহ আর এই খণ্ডটা কার্নেল স্পেইস (Kernel Space) নামে পরিচিত। আরেকটি খণ্ডে চলে বাকি সব সাধারণ প্রসেস যেমন ব্রাউসার, টেক্সট এডিটর, গেমস, ইত্যাদি আর এই খণ্ডটা ইউসার স্পেইস (User Space) নামে পরিচিত।

##### 📌**Container**
Let's revisit the different ways of deploying applications we talked about—locally, On-prem, and in the cloud. Imagine a friend, like another developer, wants to work with your code. They'd need to get their own "copy" of it. They'd go to a platform like GitHub and download your project files. Then, they'd install any extra tools needed to run your code smoothly. But sometimes, their computer might have different settings that make it hard for your code to work right. That's where containers come in handy. They wrap up your code with all the settings and tools it needs to run, no matter where it's put.

   - ###### 📌**More Defination**
      - **Containers are like pre-packaged sets of tools and code. You just plug them in, and they start working without any fuss.**
      - **Containers are predefined configurations and dependencies, along with the code files that make it possible for the code to run seamlessly.**
      - **একটা কার্নেলের ওপর আলাদা isolated ইউসার স্পেইসগুলোকে (User Space) কন্টেইনার (Container)বলা হয়.**
      - **Container is Runnable instance of the image, basically it is an isolated process.**
      - **Container is package of software that includes all dependencies: code, runtime, configuration, and system libraries so that it can run on any host system.**

<p align="right">
  <img src="https://github.com/saifulislam88/docker/assets/68442870/d3fb591d-3c6b-43ed-aa93-464187b108d2" alt="Technological Transformation" width="600"/>
</p>

###### 📌**Different Container or Container runtimes provider**

- Docker
- Podman
- Containerd
- CRI-O
- LXC

https://www.linkedin.com/posts/mmumshad_kodekloud-devops-kubernetes-activity-7153377989160751105-viax/?utm_source=share&utm_medium=member_desktop

### 🚀**Docker**

Docker is a **daemon-based** software platform that uses **OS-level virtualization** to **build, deploy, and manage applications within containers**. Containers are built from images, which in turn are constructed from Dockerfiles, providing an abstraction layer for application deployment.

So Docker is an open-source lightweight containerization technology. It allows you to automate the deployment of applications in lightweight and portable containers

<img src="https://github.com/saifulislam88/docker/assets/68442870/5b11673c-469a-4b64-8030-a1fd626c088e" alt="Technological Transformation" width="600"/>

#### 🔥**Docker Features**
- **Building**
- **Shipping**
- **Run and managing Application**
- **Compatibility**
- **Dependences**
- **Rapid Scaling**
- **Easy  and Faster Configuration**
- **Increase Productivity**
- **Application Isolation**

#### 🔥**Why Use Docker Container**
- Shifting from Monolithic to Microservices Architecture.
- Sometimes Software Does Not Work in Another System.
- Cross-platform Consistency (Windows/Linux).
- DevOps and Continuous Delivery.
- Enables faster software delivery cycles.
- Docker enables efficiency and reduces operational overheads so that any developer, in any development environment
- To help automate the deployment of applications inside containers.
- Docker enables more efficient use of system resources.
- Simplifies the application development and deployment process.
- **Collaboration’ with Docker**
<img src="https://github.com/saifulislam88/docker/assets/68442870/0851f2cb-62a7-44ac-b50c-4995e6044952" alt="Technological Transformation" width="600"/>

- **Also, the Agile Development without Docker culture results in many issues as shown in the below picture.**
<img src="https://github.com/saifulislam88/docker/assets/68442870/3dbc68a7-aca6-414d-af31-f828cd22ddfd" alt="Technological Transformation" width="600"/>

- **To overcome all these situations the need for containerization with Docker arises.**
<img src="https://github.com/saifulislam88/docker/assets/68442870/d41b0acb-99c5-4b6b-aa21-ea7df2edaa30" alt="Technological Transformation" width="600"/>

#### 🔥Docker Architecture and Components


<img src="https://github.com/saifulislam88/docker/assets/68442870/4810e275-4208-49b9-aaf2-631146eb6cbb" alt="Technological Transformation" width="600"/>


**There are five major components in the Docker architecture:**

 - Docker Daemon
 - Docker Clients
 - Docker Host
 - Docker Registry
 - Docker Images
 - Docker containers

#### 🔥Container Application Deployment lifecycle on Docker

- [Install Docker: Set up Docker on your machine & Run your first container.](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#install-docker-set-up-docker-on-your-machine--run-your-first-container)
  - [Docker Installation Steps on Ubuntu](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#--installation-steps-on-ubuntu)
  - [Run your first container using Docker Registry(Public Repo: https://hub.docker.com/)](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#--run-your-first-container-using-docker-registrypublic-repo-httpshubdockercom)
  - [Explain basic Docker usage workflow](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#--explain-basic-docker-usage-workflow)
- [Create a Dockerfile: Define your application's environment and dependencies.](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#create-a-dockerfile-define-your-applications-environment-and-dependencies)
  - [Writing a Dockerfile for a simple application | Set up a nodejs project](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#--writing-a-dockerfile-for-a-simple-application--set-up-a-nodejs-project)
  - [Create a file named app.js in your project directory and add the following code:](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#--create-a-file-named-appjs-in-your-project-directory-and-add-the-following-code)
  - [Run and Test Your Application: You should see the message Example app listening at http://localhost:3000](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#--run-and-test-your-application-you-should-see-the-message-example-app-listening-at-httplocalhost3000)
  - [Write a Dockerfile on Nodejs project](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#--write-a-dockerfile-on-nodejs-project) 
- [Build an Image: Use the Dockerfile to build a Docker image & Run from local.](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#build-an-image-use-the-dockerfile-to-build-a-docker-image--run-from-local)
- [Tag | Login | Push the Docker Image.](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#tag--login--push-the-docker-image)
- [Pull and Run : Download the image from Docker Hub on another machine | Create and run a container from the Docker image.](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#pull-and-run---download-the-image-from-docker-hub-on-another-machine--create-and-run-a-container-from-the-docker-image)
- [Manage Containers: Use Docker commands to manage the lifecycle of containers.](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#manage-containers-use-docker-commands-to-manage-the-lifecycle-of-containers)
- [Deploy Updates: Rebuild, retag, push updates, and restart the container to deploy updates.](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#deploy-updates-rebuild-retag-push-updates-and-restart-the-container-to-deploy-updates)

##### 📌**Install Docker: Set up Docker on your machine & Run your first container**
  
  ###### - ✅Installation Steps on Ubuntu

```sh
sudo apt update
sudo apt install apt-transport-https ca-certificates curl software-properties-common
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
echo "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt update
sudo apt install docker-ce
sudo systemctl status docker
```

  ###### - ✅Run your first container using Docker Registry(Public Repo: https://hub.docker.com/)

```sh
docker run -it -d -p 8080:80 --name web nginx:latest
docker run -it -d -p 80:80 --name web-nginx nginx
docker ps -a
```

   ###### - ✅Explain basic Docker usage workflow

   - **🎯1.**	Everything starts with the Dockerfile. The Dockerfile is the source code of the Image.

   - **🎯2.**	Once the Dockerfile is created, you build it to create the image of the container. The image is just the "compiled version" of the "source code" which is the Dockerfile.

   - **🎯3.**	Once you have the image of the container, you should redistribute it using the registry. The registry is like a git repository -- you can push and pull images.

   - **🎯4.**	Next, you can use the image to run containers. A running container is very similar, in many aspects, to a virtual machine (but without the hypervisor).

##### 📌**Create a Dockerfile: Define your application's environment and dependencies**

A Dockerfile is a text document that contains all the commands or instructions to bulid an image automatically by reading.

###### - ✅Writing a Dockerfile for a simple application | Set up a nodejs project

```sh
sudo apt update
sudo apt install -y nodejs npm
node -v
npm -v
mkdir my-node-app
cd my-node-app
npm init -y
npm install express
```

###### - ✅Create a file named app.js in your project directory and add the following code:

```sh
const express = require('express');
const app = express();
const port = 3000;

app.get('/', (req, res) => {
    res.send('Hello World!');
});

app.listen(port, () => {
    console.log(`Example app listening at http://localhost:${port}`);
});

```

###### - ✅Run and Test Your Application: You should see the message `Example app listening at http://localhost:3000`

`node app.js`

###### - ✅Write a Dockerfile on Nodejs project

```sh
# Use an official Node.js runtime as a parent image
FROM node:14
# Set the working directory in the container
WORKDIR /usr/src/app

# Copy the package.json and package-lock.json files
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of the application code
COPY . .

# Make port 3000 available to the world outside this container
EXPOSE 3000

# Run the app
CMD ["node", "app.js"]

```

##### 📌Build an Image: Use the Dockerfile to build a Docker image & Run from local

`docker build -t my-node-app .`

`docker run -it -d -p 3000:3000 my-node-app`

##### 📌Tag | Login | Push the Docker Image

`docker tag my-node-app saifulislam88/my-node-app:latest`
  
`docker login`

`docker push saifulislam88/my-node-app:latest`

##### 📌Pull and Run :  Download the image from Docker Hub on another machine | Create and run a container from the Docker image

`docker pull saifulislam88/my-node-app:latest`

`docker run -it -d -p 3001:3000 saifulislam88/my-node-app:latest`

`docker ps -a`

##### 📌Manage Containers: Use Docker commands to manage the lifecycle of containers
##### 📌Deploy Updates: Rebuild, retag, push updates, and restart the container to deploy updates
What are the Common instructions in Dockerfile?












![image](https://github.com/saifulislam88/docker/assets/68442870/0e56ca7a-8b0e-455b-8b8e-ae92660e00e4)
