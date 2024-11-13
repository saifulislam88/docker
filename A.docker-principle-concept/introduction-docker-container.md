## **Docker Container Administration | An Introduction & Principle Concept**<br>

<img src="https://github.com/saifulislam88/docker/assets/68442870/09012688-7671-4f50-8208-dedad3b66353" alt="Signature" width="400"/>

&nbsp;&nbsp;**Copyright** © 2024 Md. Saiful Islam(**mSI**). All Rights Reserved | **Internet & ChatBot**<br>
<br>
## &nbsp;&nbsp;**Table of Contents**
- [Technological Transformation](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#technological-transformation---bare-metal---virtualization--container--cloud)
  - [What are key reasons for Bare Metal -> Virtualization -> Container -> Cloud Transition](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#technological-transformation---bare-metal---virtualization--container--cloud)
- [Bare Metal](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#bare-metal)
  - [Bare Metal Features](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#bare-metal-features)
- [Virtualization](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#virtualization)
  - [Virtualization-Features](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#virtualization-features)
- [Types of Virtualization Technologies](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#types-of-virtualization-technologies)
   - [KVM Virtualization](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#virtualization)
       - [KVM Features](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#kvm-features)
   - [OS Virtualization](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#os-virtualization)
      - [Container](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#container)
         - [More Defination](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#more-defination)
         - [Different Container or Container runtimes provider](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#different-container-or-container-runtimes-provider)
         - [What is Docker](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#docker)
          - [Docker Features](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#docker-features)
          - [Why We should use Docker Container](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#why-use-docker-container)
          - [Docker Architecture and Components](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#docker-architecture-and-components)
          - [Container Based Application Deployment Steps On Docker](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#container-application-deployment-lifecycle-on-docker)
           - [Explain Basic Docker Usage Workflow](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#explain-basic-docker-usage-workflow)
           - [Installation Steps on Ubuntu](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#installation-steps-on-ubuntu)
           - [Run Your First Container using Docker Registry](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#run-your-first-container-using-docker-registrypublic-repo-httpshubdockercom)
           - [Deploy & Manage Your Own Container & Image](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#deploy--manage-your-own-container--image)
              - [Single-Stage Docker Images & Containers | Application Deployment](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#single-stage-docker-images--containers--application-deployment)
                - [Writing a Simple Application on Nodejs](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#writing-a-simple-application-on-nodejs)
                - [Create a File Named `app.js` and Add the Following Code](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#create-a-file-named-appjs-and-add-the-following-code)
                - [Run and Test Your Application in Host Machine](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#run-and-test-your-application-in-host-machine)
                - [Write a Dockerfile on Nodejs Application](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#write-a-dockerfile-on-nodejs-application)
                - [Build an Image: Use the Dockerfile to build a Docker image & Run from local Image](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#build-an-image-use-the-dockerfile-to-build-a-docker-image--run-from-local-image)
                - [Tag | Login | Push the Docker Image](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#tag--login--push-the-docker-image)
                - [Pull and Run - Download the image from Docker Hub](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#pull-and-run---download-the-image-from-docker-hub)
             - [Multi-Stage Docker Images & Containers | Application Deployment](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#multi-stage-docker-images--containers--application-deployment)
                - [Benefits & Importance of Multi-Stage Builds](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#benefits--importance-of-multi-stage-builds)
                - [Find the following Multi-Stage Dockerfile](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#find-the-following-multi-stage-dockerfile)
                - [How It Works](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#how-it-works)
                - [Compare Single-Stage Image vs Muti-Stage Image](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#compare-single-stage-image-vs-muti-stage-image)
                - [Build an Image: Use the Dockerfile to build a Docker image & Run from local Image](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#build-an-image-use-the-dockerfile-to-build-a-docker-image--run-from-local-image---multi-stage)
                - [Tag | Login | Push the Docker Image](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#tag--login--push-the-docker-image---multi-stage)
                - [Pull and Run - Download the image from Docker Hub](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#pull-and-run---download-the-image-from-docker-hub---multi-stage)
             - [Composer-Based Docker Images & Containers | Application Deployment](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#composer-based-docker-images--containers--application-deployment)
          - [The instructions/Commands list in Dockerfile](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#-the-instructionscommand-list-in-dockerfile)
              - [FROM](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#-from)
              - [WORKDIR](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#workdir)
              - [USER](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#user)
              - [MAINTAINER](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#maintainer)
              - [LABEL](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#label)
              - [COPY and ADD](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#copy-and-add)
              - [RUN | CMD | ENTRYPOINT](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#run--cmd--entrypoint)
              - [EXPOSE](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#expose)
              - [VOLUME](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#volume)
          - [Manage Containers: Use Docker commands to manage the lifecycle of containers.](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#manage-containers-use-docker-commands-to-manage-the-lifecycle-of-containers)
          - [Deploy Updates: Rebuild, retag, push updates, and restart the container to deploy updates.](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#deploy-updates-rebuild-retag-push-updates-and-restart-the-container-to-deploy-updates)
          - [Docker Networking](#docker-networking---unlocking-the-mysteries-of-networks)
          - [Docker Volumes and Storage](#Docker-Volumes-and-Storage)
          - [Docker Compose overview](#Docker-Compose-overview)
### 🚀**Technological Transformation - Bare Metal -> Virtualization -> Container -> Cloud**

<p align="right">
<img src="https://github.com/saifulislam88/docker/assets/68442870/401f1965-77cb-450a-b558-5ad80b1428ea" alt="Technological Transformation" width="800"/>
</p>

🔗 **`Bare-Metal-> Virtualization:`** To improve resource utilization, flexibility, and isolation while maintaining control over the hardware.\
🔗 **`Virtualization-> Cloud:`** To leverage scalability, cost efficiency, reduced maintenance, and global accessibility, enabling faster innovation and business agility.\
🔗 **`Example:`** Instead of having ten servers each running at 10% capacity, virtualization can consolidate them into one or two servers running at 80-90% capacity.

<br>

### 🚀**Bare Metal**

**Bare Metal** refers to a type of computing infrastructure where an application or service is run directly on physical hardware **without any intervening layers of virtualization or containerization**.

- #### 🔥**Bare Metal Features**

    - **Performance:** Direct access to hardware, no virtualization overhead.
    - **Control:** Full control over the hardware and software stack.
    - **Use Case:** High-performance computing, gaming servers, financial trading systems.

<br>

### 🚀**Virtualization**

**Virtualization is software technology that separates physical infrastructures to create multiple virtual machine (VM) or virtual environments on a single server.**

This software technology of virtualization system is known as a virtual machine monitor (VMM) or virtual manager, which separates compute environments from the actual physical infrastructure–this makes it possible to run several operating systems on one computer at the same time. 
**A virtual machine monitor or VMM, also known as a hypervisor, is software that creates, runs and manage virtual machines (VMs).**

  - #### 🔥**Virtualization Features**

     - **Resource Utilization:** Better utilization of physical hardware by running multiple VMs.
     - **Isolation:** Strong isolation between applications.
     - **Flexibility:** Easier to create, manage, and scale VMs.
     - **Use Case:** Server consolidation, development and testing environments.

<p align="right">
<img src="https://github.com/saifulislam88/docker/assets/68442870/3c392818-aa43-4313-8893-72d83f1a5019" alt="Technological Transformation" width="800"/>
</p>

  - #### 🔥**Types of Virtualization Technologies**
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;There are **two** main types of virtualization technologies<br>
 
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 🛠️ **KVM Virtualization | VM**\
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 🛠️ **OS Virtualization | Container**

### 🚀KVM Virtualization

**KVM (Kernel-Based Virtual Machine) Is An Open-Source Virtualization Technology That Allows You To Run Multiple Virtual Machines (VMs) On A Linux/Windows Host**. A Kernel-based Virtual Machine (KVM) allows you to turn Linux or Windows Server into a hypervisor, allowing your operating system to produce multiple virtual machines and isolated virtual environments.

🛠️**Type 1 - hypervisor** is running on **bare-metal hardware**. Such hypervisors are VMWare ESXi, Linux KVM, Hyper-V\
🛠️**Type 2 - hypervisor** is running inside **Host OS**. Such hypervisors are VMWare Workstation are Oracle VirtualBox


![image_resized_for_md](https://github.com/user-attachments/assets/bf1e5dae-6f4c-4789-8ce0-99e505726ef3)


- ####  🔥KVM Features
     - **Security**
     - **Storage**
     - **Hardware support**
     - **Memory management**
     - **Live migration**
     - **Performance and scalability**
     - **Scheduling and resource control**
     - **Lower latency and higher prioritization**

### 🚀OS Virtualization

**একটি কার্নেলের ওপর একাধিক isolated ইউসার স্পেইসের অস্তিত্বকে অপারেটিং সিস্টেম লেভেল ভার্চুয়ালাইজেসন বলে.** প্রতিটা ইউসার স্পেইসের রানটাইম এনভায়রনমেন্ট, ইউসার সেটিংস, ইত্যাদি ভিন্ন। আর একটা ইউসার স্পেইসের প্রসেস আরেকটা ইউসার স্পেইসে প্রবেশ করতে পারে না। মানে মেমোরি প্রটেকশন.

**User Space and Kernel Space**

অপারেটিং সিস্টেমে কিছু প্রসেস আছে যাদের সিস্টেম রিসোর্সগুলো (System Resource) সরাসরি অ্যাক্সেস করার প্রিভিলেজ (Privilege) থেকে থাকে। এই প্রসেসগুলো সাধারণত কার্নেল (Kernel) এবং ডিভাইস ড্রাইভার (Device Drivers) হয়ে থাকে। এসমস্ত প্রিভিলেজসম্পন্ন প্রসেসসমুহের মেমোরি প্রটেকশনের জন্যে ভার্চুয়াল মেমোরি স্পেইসের একাংশকে dedicate করে দেয়া হয় । এর কারনে ভার্চুয়াল মেমোরি দ্বিখণ্ডিত হয় । একটি খণ্ডে চলে কার্নেল আর ডিভাইস ড্রাইভারদের মত প্রিভিলেজ সম্পন্ন প্রসেসসমুহ আর এই খণ্ডটা কার্নেল স্পেইস (Kernel Space) নামে পরিচিত। আরেকটি খণ্ডে চলে বাকি সব সাধারণ প্রসেস যেমন ব্রাউসার, টেক্সট এডিটর, গেমস, ইত্যাদি আর এই খণ্ডটা ইউসার স্পেইস (User Space) নামে পরিচিত।

#### 🔥**Container**

Let's revisit the different ways of deploying applications we talked about—locally, On-prem, and in the cloud. Imagine a friend, like another developer, wants to work with your code. They'd need to get their own "copy" of it. They'd go to a platform like GitHub and download your project files. Then, they'd install any extra tools needed to run your code smoothly. But sometimes, their computer might have different settings that make it hard for your code to work right. That's where containers come in handy. They wrap up your code with all the settings and tools it needs to run, no matter where it's put.

   - ##### 📌**More Definition**
      - **Containers are like pre-packaged sets of tools and code. You just plug them in, and they start working without any fuss.**
      - **Containers are predefined configurations and dependencies, along with the code files that make it possible for the code to run seamlessly.**
      - **একটা কার্নেলের ওপর আলাদা isolated ইউসার স্পেইসগুলোকে (User Space) কন্টেইনার (Container)বলা হয়.**
      - **Container is Runnable instance of the image, basically it is an isolated process.**
      - **Container is package of software that includes all dependencies: code, runtime, configuration, and system libraries so that it can run on any host system.**

<p align="right">
  <img src="https://github.com/saifulislam88/docker/assets/68442870/d3fb591d-3c6b-43ed-aa93-464187b108d2" alt="Technological Transformation" width="600"/>
</p>

   - ##### 📌**Different Container or Container runtimes provider**

       - Docker
       - Podman
       - Containerd
       - CRI-O
       - LXC

[More Details](https://www.linkedin.com/posts/mmumshad_kodekloud-devops-kubernetes-activity-7153377989160751105-viax/?utm_source=share&utm_medium=member_desktop)


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


**There are major components in the Docker architecture:**

 - Docker Daemon
 - Docker Clients
 - Docker Host
 - Dockerfile

   A **Dockerfile** is a text document that contains all the commands or instructions to bulid an image automatically by reading.

 - Docker Registry
 - Docker Images
 - Docker containers
 - Docker Composer

### 🔥Container Application Deployment Steps on Docker

![image](https://github.com/user-attachments/assets/3533c007-57de-41ac-8d92-42006c4f96ee)




- [Explain Basic Docker Usage Workflow](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#explain-basic-docker-usage-workflow)
- [Installation Steps on Ubuntu](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#installation-steps-on-ubuntu)
- [Run Your First Container using Docker Registry](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#run-your-first-container-using-docker-registrypublic-repo-httpshubdockercom)
- [Deploy & Manage Your Own Container & Image](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#deploy--manage-your-own-container--image)
   - [Single-Stage Docker Images & Containers | Application Deployment](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#single-stage-docker-images--containers--application-deployment)
     - [Writing a Simple Application on Nodejs](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#writing-a-simple-application-on-nodejs)
     - [Create a File Named `app.js` and Add the Following Code](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#create-a-file-named-appjs-and-add-the-following-code)
     - [Run and Test Your Application in Host Machine](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#run-and-test-your-application-in-host-machine)
     - [Write a Dockerfile on Nodejs Application](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#write-a-dockerfile-on-nodejs-application)
     - [Build an Image: Use the Dockerfile to build a Docker image & Run from local Image](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#build-an-image-use-the-dockerfile-to-build-a-docker-image--run-from-local-image)
     - [Tag | Login | Push the Docker Image](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#tag--login--push-the-docker-image)
     - [Pull and Run - Download the image from Docker Hub](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#pull-and-run---download-the-image-from-docker-hub)
  - [Multi-Stage Docker Images & Containers | Application Deployment](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#multi-stage-docker-images--containers--application-deployment)
     - [Benefits & Importance of Multi-Stage Builds](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#benefits--importance-of-multi-stage-builds)
     - [Find the following Multi-Stage Dockerfile](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#find-the-following-multi-stage-dockerfile)
     - [How It Works](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#how-it-works)
     - [Compare Single-Stage Image vs Muti-Stage Image](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#compare-single-stage-image-vs-muti-stage-image)
     - [Build an Image: Use the Dockerfile to build a Docker image & Run from local Image](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#build-an-image-use-the-dockerfile-to-build-a-docker-image--run-from-local-image---multi-stage)
     - [Tag | Login | Push the Docker Image](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#tag--login--push-the-docker-image---multi-stage)
     - [Pull and Run - Download the image from Docker Hub](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#pull-and-run---download-the-image-from-docker-hub---multi-stage)
  - [Composer-Based Docker Images & Containers | Application Deployment](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#composer-based-docker-images--containers--application-deployment)

#### ✅Explain Basic Docker Usage Workflow

   - **🎯1.**	Everything starts with the Dockerfile. The Dockerfile is the source code of the Image.

   - **🎯2.**	Once the Dockerfile is created, you build it to create the image of the container. The image is just the "compiled version" of the "source code" which is the Dockerfile.

   - **🎯3.**	Once you have the image of the container, you should redistribute it using the registry. The registry is like a git repository -- you can push and pull images.

   - **🎯4.**	Next, you can use the image to run containers. A running container is very similar, in many aspects, to a virtual machine (but without the hypervisor).

#### ✅Installation Steps on Ubuntu

```sh
sudo apt update
sudo apt install apt-transport-https ca-certificates curl software-properties-common
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
echo "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt update
sudo apt install docker-ce
sudo systemctl status docker
```
#### ✅Run Your First Container using Docker Registry(Public Repo: https://hub.docker.com/)

```sh
docker run -it -d -p 8080:80 --name web nginx:latest
docker run -it -d -p 80:80 --name web-nginx nginx
docker ps -a
```
#### ✅Deploy & Manage Your Own Container & Image

### 🚀Single-Stage Docker Images & Containers | Application Deployment

- #### 📌Writing a Simple Application on Nodejs

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

   - #### 📌Create a File Named `app.js` and Add the Following Code

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

   - #### 📌Run and Test Your Application in Host Machine

You should see the message `Example app listening at http://localhost:3000`

`node app.js`

   - #### 📌Write a Dockerfile on Nodejs Application

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

   - #### 📌Build an Image: Use the Dockerfile to build a Docker image & Run from local Image

`docker build -t my-node-app .`

`docker run -it -d -p 3000:3000 my-node-app`

   - #### 📌Tag | Login | Push the Docker Image

`docker tag my-node-app saifulislam88/my-node-app:latest`
  
`docker login`

`docker push saifulislam88/my-node-app:latest`

   - #### 📌Pull and Run - Download the image from Docker Hub

`docker pull saifulislam88/my-node-app:latest`

`docker run -it -d -p 3001:3000 saifulislam88/my-node-app:latest`

`docker ps -a`


### 🚀Multi-Stage Docker Images & Containers | Application Deployment

Multi-stage Dockerfile is an essential feature provided by Docker that allows developers to create more efficient and smaller Docker images, resulting in faster builds, reduced image sizes, and improved security.

 #### 📌**Benefits & Importance of Multi-Stage Builds**
   
   - Reduced Image Size
   - Faster Build Times
   - Improved Security
   - Simplified Build Pipeline
   - Portability and Consistency


Here is the real example of Multi-Stage Dockerfile. We converted [Single-Stage Dockerfile](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#write-a-dockerfile-on-nodejs-application) to Multi-Stage Dockerfile in below.

#### **Find the following Multi-Stage Dockerfile**
```sh
# Stage 1: Build
FROM node:14 as build

# Set the working directory in the container
WORKDIR /usr/src/app

# Copy the package.json and package-lock.json files
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of the application code
COPY . .

# Stage 2: Production
FROM node:14-slim

# Set the working directory in the container
WORKDIR /usr/src/app

# Copy only the necessary files from the build stage
COPY --from=build /usr/src/app .

# Make port 3000 available to the world outside this container
EXPOSE 3000

# Run the app
CMD ["node", "app.js"]

```
-  #### 📌**How It Works**

   - **Build Stage**

      - The first stage (`build`) uses the `node:14` image to set up the build environment.
      - It sets the working directory, copies the `package.json` and `package-lock.json` files, and installs the dependencies using `npm install`.
      - It then copies the rest of the application code.

   - **Production Stage:**

      - The second stage (`production`) uses a lighter `node:14-slim` image, which is smaller and optimized for production use.
      - It sets the working directory and copies the necessary files from the `build` stage using `COPY --from=build`.
      - It exposes port `3000` and specifies the command to run the application.

  - #### 📌Compare Single-Stage Image vs Muti-Stage Image
  
`docker image ls`

  - #### 📌Build an Image: Use the Dockerfile to build a Docker image & Run from local Image - Multi-Stage 

`docker build -t my-node-app .`

`docker run -it -d -p 3000:3000 my-node-app`

   - #### 📌Tag | Login | Push the Docker Image - Multi-Stage 

`docker tag my-node-app saifulislam88/my-node-app:latest`
  
`docker login`

`docker push saifulislam88/my-node-app:latest`

   - #### 📌Pull and Run - Download the image from Docker Hub - Multi-Stage 

`docker pull saifulislam88/my-node-app:latest`

`docker run -it -d -p 3001:3000 saifulislam88/my-node-app:latest`

`docker ps -a`


### 🚀Composer-Based Docker Images & Containers | Application Deployment

##### 📌 The instructions/Command list in Dockerfile

- [FROM](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#-from)
- [WORKDIR](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#workdir)
- [USER](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#user)
- [MAINTAINER](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#maintainer)
- [LABEL](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#label)
- [COPY and ADD](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#copy-and-add)
- [RUN | CMD | ENTRYPOINT](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#run--cmd--entrypoint)
- [EXPOSE](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#expose)
- [VOLUME](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#volume)

 ###### ✅ **FROM**
 **Instruction creates the base image layer from base a image**.In every valid Dockerfile, FROM is the first instruction.

  &nbsp;&nbsp; **Example:**

```sh
FROM alpine:latest
FROM node:14
FROM python:3.8-slim
FROM ubuntu:20.04
```

###### ✅**WORKDIR**
Sets the working directory for any `RUN`, `CMD`, `ENTRYPOINT`, `COPY`, and `ADD` instructions that follow it in the Dockerfile.If you set `WORKDIR` multiple times, each `WORKDIR` instruction will override the previous one.

   &nbsp;&nbsp; **Example:**
```sh
# Set the working directory to /app
WORKDIR /usr/src/app

# Change working directory to /usr/src/app
WORKDIR /app

# Change working directory back to /app
WORKDIR /usr/src/app

```

###### ✅**USER**
Sets the user name (or UID) and optionally the user group (or GID) to use when running the image and for any `RUN`, `CMD`, and `ENTRYPOINT` instructions that follow it in the Dockerfile.

```sh
USER appuser
```
###### ✅**MAINTAINER**
The MAINTAINER instruction was used in older versions of Docker to specify the person responsible for the Dockerfile or image.Metadata of the owner who owns the image

```sh
MAINTAINER Saiful Islam <saiful.islam@example.com>
```
###### ✅**LABEL**

The `LABEL` instruction is used to add metadata to an image. It is more versatile and can be used to specify the maintainer along with other metadata like version, description, and more.

```sh
LABEL maintainer="Saiful Islam <saiful.islam@example.com>"
LABEL version="1.0"
LABEL description="A simple nodejs application"
```

###### ✅**COPY and ADD**
In Dockerfiles, both the `COPY` and `ADD` instructions are used to copy files and directories from the host machine into the Docker image. However, there are some key differences between the two:


  - 🎯**COPY**
Only copies files and directories. It doesn't have additional capabilities like extracting archives.`COPY` is preferred for copying files and directories because it is simple and predictable.

```sh
# Set the working directory to /app
WORKDIR /app

# Copy local source code to /app using COPY
COPY . .

# OR We can copy local source code to /app using COPY
COPY . /app
COPY requirements.txt ./
```

   - 🎯**ADD**

**The `ADD` instruction is similar to COPY but with some additional features**. `ADD` is useful for specific cases where you need **to extract archives or download files from URLs**. If the source is a local tar archive (`e.g., a .tar, .tar.gz, .tar.bz2, etc.`), it will be automatically unpacked at the destination. Can add files from remote URLs. If the source is a URL, ADD downloads the file from the URL and adds it to the destination path.

```sh
# Set the working directory to /app
WORKDIR /app
ADD . /app
ADD app.tar.gz /app

# Download a file from a URL and add it to the /app directory
ADD https://example.com/somefile.tar.gz /app/
ADD https://example.com/somefile.txt /app/
```

##### **✅RUN | CMD | ENTRYPOINT**

In a Dockerfile, RUN, CMD, and ENTRYPOINT are instructions used to define commands that should be run in the container. They have distinct purposes and behaviors. Additionally, each of these instructions can be specified in either **`shell` form** or **`exec` form**. That means, there are two ways to specify the command to run. `RUN` `CMD` `ENTRYPOINT` supports both form.

**Shell form** 
The command is run inside a new shell process, which, by default, is /bin/sh -c on Linux and cmd /S /C on Windows. Each command runs in a shell (/bin/sh -c), which might not exist in some minimal base images.

```sh
# Example of writing in Dockerfile
RUN apt-get update && apt-get install -y python3
CMD python app.py
ENTRYPOINT python app.py
```

**Exec form**
This command is not run inside a new shell process. The exec form uses a JSON array and does not invoke a shell unless explicitly done.


```sh
# Example of writing in Dockerfile
RUN ["apt-get", "update"]
CMD ["python", "app.py"]
ENTRYPOINT ["python", "app.py"]
```


🎯- **RUN**

**RUN** command is mainly used to install a new software packages and applications on top of an existing image layer `[FROM ubuntu: latest]` in Dockerfile. When you use the `RUN` command, it will execute the instruction and will create a new layer.

**Example from `Shell` form**

```sh
RUN apt-get -y update
RUN apt-get install vim && apt-get install -y libpq-dev
```

**Example from `Exec` form**

```sh
RUN ["apt-get", "update"]
RUN ["apt-get", "install", "vim"]
```


🎯- **CMD**

**CMD** in Dockerfile Instruction is used to execute a command in running container, **there should be one CMD in a Dockerfile.**
CMD executes the **final** commands when you launch a new container from image and also we use CMD command to provide default values of an executing container. **In a Dockerfile, if we include multiple CMD commands, then only the last instruction is used.**

```sh
FROM python:3.8-slim

# Set the working directory
WORKDIR /app

# Copy the application files
COPY . /app

# Install dependencies
RUN pip install -r requirements.txt

# Set the entrypoint
ENTRYPOINT ["python"]

# Set the default command arguments
CMD ["app.py"]

```
This **CMD** sets the default command to run **python app.py** when the container starts. That means python app.py parameters will be **ENTRYPOINT**



🎯- **ENTRYPOINT**

The ENTRYPOINT instruction defines the command that will always be run, while CMD provides the default arguments for that command. However, if you specify both CMD and ENTRYPOINT with the same command, it can lead to unintended behavior.


```sh
FROM python:3.8-slim

# Set the working directory
WORKDIR /app

# Copy the application files
COPY . /app

# Install dependencies
RUN pip install -r requirements.txt

# Set the entrypoint to python
ENTRYPOINT ["python"]

# Set the default command to app.py
CMD ["app.py"]

```
**Explanation:**

The **ENTRYPOINT** specifies **python** as the executable. The CMD provides **app.py** as the default argument. When running the container, the default command will be **python app.py**. If both `CMD` and `ENTRYPOINT` specify the same command, it can lead to repeated commands and unintended behavior. For example:

```sh
ENTRYPOINT ["python", "app.py"]
CMD ["python", "app.py"]
```


###### ✅**EXPOSE**

Make port 80 available to the world outside this container

`EXPOSE 80`

###### ✅**VOLUME**

Create a volume at /data

`VOLUME ["/data"]`

##### 📌Manage Containers: Use Docker commands to manage the lifecycle of containers
##### 📌Deploy Updates: Rebuild, retag, push updates, and restart the container to deploy updates


<br>
<br>

**-------------------------------------------------------------------------------------------------------------------------------------------------------------**

### [Docker Networking - Unlocking the Mysteries of Networks]()

Docker leverages networking for container communication. Docker has a pluggable networking system where plugins are called drivers.

<br>

![image](https://github.com/user-attachments/assets/6a503a71-b141-4682-9865-f563de14c07e)


**Networking Models:**

### - [**Docker Single Host Networking**](#Docker-Single-Host-Networking)

Docker Single Host Networking provides communication between containers on the same host via a virtual network bridge, allowing for smooth interaction while isolating them from external networks.

 - [Bridge (default)](#Bridge-default)
 - [Bridge (user-defined)](#Bridge-user-defined)
 - [Host](#host)
 - [None](#none)
<br>

![image](https://github.com/user-attachments/assets/8e500731-2f5f-46b2-9334-71dfaef2cfae)

<br>

### 📌 Bridge (default)

When docker containers are created without specifying a network, they are automatically placed in the default bridge network. Where it works like - **`Bridge<NAT<docker0`**


`ip a`\
`ip addr show`\
`docker network ls`\
`docker network inspect bridge`\
**`docker run -d --name my_container nginx`**\
**`docker run -dit --name Rock nginx`**\
`docker ps`\
`docker inspect <container_id_or_name>`\
`docker inspect <container_id_or_name> | grep "IPAddress"`\
`docker inspect <container_id_or_name> | egrep "MacAddress|IPAddress"`\
**`docker network ls`\
`docker network disconnect <network_name> <container_id_or_name>`\
`docker inspect 1fe4bc908ce9 | grep IP`\
`docker network connect <network_name> <container_id_or_name>`\
`docker inspect <container_id_or_name> | grep IP`**

**To change the default IP address range used by Docker's docker0 bridge network, you need to modify the Docker daemon's configuration.**


**`sudo systemctl stop docker`\
`sudo vim /etc/docker/daemon.json`**

```sh
{
  "bip": "192.168.1.1/24"
}

```
**`sudo systemctl start docker`\
`ip addr show docker0`**

<br>




### 📌 Bridge (user-defined)

This network type is similar to the user-defined bridge network. It also creates an internal private network within the host, but it does not come already created by Docker. You have to create it yourself.
`Bridge - NAT - <network_name>`


`ip a`\
`ip addr show`\
`docker network ls`\
`docker network inspect bridge`\
`docker ps`\
`docker run -d --name my_container nginx`\
`docker network create my_custom_network` | `docker network create my_flask_network`\
`docker network inspect my_custom_network`\
`docker network create --driver bridge mycustom_bridge`\
`docker network create --subnet=192.168.10.0/24 my_custom_network`\
`docker run -d --name my_container nginx`\
`docker run -d --name my_container --network my_custom_network nginx`\
`docker run -d --name container1 --network my_custom_network nginx`\
`docker run -d --name container2 --network my_custom_network alpine sleep 3600`\
`docker ps`\
`docker inspect <container_id_or_name>`\
`docker inspect <container_id_or_name> | grep "IPAddress"`\
`docker inspect a907e362bf59 | egrep "MacAddress|IPAddress"`\
docker network connect my_custom_network <container_id_or_name>
docker network disconnect my_custom_network <container_id_or_name>

docker network rm
docker inspect -f "{{range.NetworkSettings.Networks}}{{.IPAddress}}{{end}}"


### 📌 Host

Containers in host network mode directly utilize your host's network stack, lacking isolation. They do not receive separate IP addresses, and any port bindings are directly exposed on your host's network interface. In practical terms, if a container process is configured to listen on port 80, it will bind to your host machine's IP address on port 80.

- The container shares the host’s networking namespace
- Container’s network stack is not isolated from the Docker host
- No `veth` pairs are created on host. All network interfaces of the host are visible inside the container.
- All routing of host computer is visible inside the container.
- No IP address is allocated to the container, it shares it with the host.
- Port-mapping does not take effect. “-p”, and “-P” options are ignored. Whatever the port of the application inside the container, it is available as-is on the host’s IP address.
- Useful to optimize performance, as it does not require NAT between host and container. No “userland-proxy” is created for each port of the container.
- Host networking only works on Linux hosts

`ip a`\
`ip addr show`\
`docker network ls`\
`docker network inspect host`\
`docker ps`\
`docker stop $(docker ps -q) && docker rm $(docker ps -a -q)`\
`docker ps -a`\
**`docker run -d --network host --name my_nginx nginx`**\
`docker ps`\
`docker inspect <container_id_or_name> | grep IP`**

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

### 📌 None

None is a docker network-type where the container is not attached to any network. As a result, the container is unable to communicate with any external network or other containers. It is isolated from every other network.

```sh
docker run -d --network none --name my_nginx nginx
```

### - [**Docker Multi-Host Networking**](Docker-Multi-Host-Networking)

Docker Multi-Host Networking enables containers running on various hosts to communicate with one another via overlay networks, offering seamless connectivity across distributed settings while abstracting underlying network difficulties.

 - **Overlay**
 - **Macvlan**
 - **3rd party network plugins**
<br>

  ![image](https://github.com/user-attachments/assets/beaa9b37-8a43-4ded-ad2c-ca47f52b0b33)

<br>

 - Overlay - Swarm mode
 - Macvlan - Legacy applications needing direct connection to physical network
 - 3rd party network plugins


#### Docker Volumes and Storage

Docker volumes are persistent storage that can be used by containers to store data outside the container filesystem.

`docker run -d --name my_app --network my_flask_network -v my_flask_volume:/app my_flask_app`

## Types of Docker Storage:

## Volumes:

▶ Managed by Docker. Persist across container restarts and removals.
▶ Stored in Docker's default location (/var/lib/docker/volumes).
▶ Can be shared between multiple containers.


## Bind Mounts:

▶ Mount a host directory into the container.
▶ Can be used for accessing local files on the host.
▶ Requires absolute path on host machine.
▶ Changes in files are reflected both on host and container.


## tmpfs Mounts:

▶ Temporary storage in memory.
▶ Does not persist data after container stop/restart.
▶ Useful for sensitive or ephemeral data.


## When to Use:

**Volumes:** For data that needs to persist across container restarts.
**Bind Mounts:** When you need to access or modify files on the host system.
**tmpfs:** For temporary or secure data storage that doesn’t need persistence.

**Key Benefits of Volumes:**

Easy backup, restore, and migration.
Better performance (especially with databases).
Isolation from container lifecycle.




![image](https://github.com/saifulislam88/docker/assets/68442870/0e56ca7a-8b0e-455b-8b8e-ae92660e00e4)



#### Docker Compose 


1. Install Docker (if not already installed)

sudo apt-get update
sudo apt-get install -y docker.io

2. Download the Latest Docker Compose

sudo curl -L "https://github.com/docker/compose/releases/latest/download/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
sudo ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose
docker-compose --version


