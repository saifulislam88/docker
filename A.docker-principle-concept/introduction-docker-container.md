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
