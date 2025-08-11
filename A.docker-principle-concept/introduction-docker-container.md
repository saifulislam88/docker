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


`docker tag my-node-app saifulislam88/my-node-app:latest`
  
`docker login`

`docker push saifulislam88/my-node-app:latest`

   - #### 📌Pull and Run - Download the image from Docker Hub - Multi-Stage 

`docker pull saifulislam88/my-node-app:latest`

`docker run -it -d -p 3001:3000 saifulislam88/my-node-app:latest`

`docker ps -a`


### 🚀Composer-Based Docker Images & Containers | Application Deployment



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


## Docker Volumes and Storage

Docker volumes are persistent storage that can be used by containers to store data outside the container filesystem.

### When to Use Docker Volumes?
Volumes are designed to support the deployment of stateful Docker containers. You’ll need to use a volume when a container requires persistent storage to permanently save new and modified files.

- Typical volume use cases include the following:

 - Database storage
 - Application data 
 - Essential caches
 - Convenient data backups
 - Share data between containers 
 - Write to remote filesystems 

docker run -it -v demo_volume:/data ubuntu:22.04
docker run -it -d -v /demo_volume1:/data ubuntu:22.04
`docker run -d --name my_app --network my_flask_network -v my_flask_volume:/app my_flask_app`

## [Types of Docker Storage](https://virtualizationreview.com/articles/2022/12/22/docker4.aspx)

## Named Volumes:

▶ Managed by Docker. Persist across container restarts and removals.\
▶ Stored in Docker's default location (/var/lib/docker/volumes).\
▶ Can be shared between multiple containers.


## Bind Mounts:

▶ Mount a host directory into the container.\
▶ Can be used for accessing local files on the host.\
▶ Requires absolute path on host machine.\
▶ Changes in files are reflected both on host and container.


## tmpfs Mounts:

▶ Temporary storage in memory.\
▶ Does not persist data after container stop/restart.\
▶ Useful for sensitive or ephemeral data.



### 📌Example 1: Running a Nginx Server with tmpfs for Logs

`docker run -d --name nginx_tmpfs --tmpfs /var/log/nginx:rw,size=100M -p 8080:80 nginx`\
`docker exec -it nginx_tmpfs df -h /var/log/nginx`\
`docker exec -it nginx_tmpfs ls -l /var/log/nginx`

### 📌Example 2: PostgreSQL with tmpfs for Temporary Tables
`docker run -d --name postgres_tmpfs --tmpfs /var/lib/postgresql/tmp:rw,size=200M -e POSTGRES_USER=admin -e POSTGRES_PASSWORD=secret@123 -p 5432:5432 postgres`\
`docker exec -it postgres_tmpfs df -h /var/lib/postgresql/tmp`\
`docker exec -it postgres_tmpfs ls -l /var/lib/postgresql/tmp`


## When to Use:

**Volumes:** For data that needs to persist across container restarts.\
**Bind Mounts:** When you need to access or modify files on the host system.\
**tmpfs:** For temporary or secure data storage that doesn’t need persistence.

**Key Benefits of Volumes:**

Easy backup, restore, and migration.\
Better performance (especially with databases).\
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


