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

---

<img width="1828" height="1010" alt="docker_registry_flow_enhanced" src="https://github.com/user-attachments/assets/b5b6fd15-b8bc-441c-bd3d-82365db03ac1" />

<br> <br>
🔥**There are major components in the Docker architecture:**

 - **Docker Daemon** (Engine | Executes the container operation)
   - `/var/run/docker.sock`
 - **Docker CLI** (actual command-line tool | You type a command)
    - `/usr/bin/docker` 
    - `docker run` |  `docker ps` | `docker build`
 - **Docker Client**
    - Sends REST request to Docker daemon (`docker`) via UNIX socket (`/var/run/docker.sock`)
 - **Containerd**
 - **Container-shim**
    - It's a small and lightweight process spawned by containerd for each containerthat acts as a middle layer between `containerd  →  containerd-shim  →  runc → Linux kernel`
    - Its purpose is to:
      - Keep the container alive even if containerd crashes or is stopped.
      - Avoid zombie processes
      - Provide stdio/stderr pipes to runc
      - Allow containerd to be upgraded/restarted without stopping containers.
      - `ps aux | grep containerd-shim` `sudo pkill -f containerd-shim` `sudo kill <pid>`
 - **runc**
    - `containerd-shim` then launches `runc` to create the actual container (Linux process with `namespaces/cgroups`) communicating with `Host Kernel`. After runc finishes setup and exits, the container keeps running with `containerd-shim` as its parent process.
    - docker → containerd → containerd-shim → runc → Linux kernel → nginx container
 - **Namespace**
    - https://github.com/saifulislam88/DevOps/blob/master/Must-Know-Concepts/Systems/namespace-and-cgroup.md#what-is-a-namespace 
 - **CGroups**
    - https://github.com/saifulislam88/DevOps/blob/master/Must-Know-Concepts/Systems/namespace-and-cgroup.md#what-is-a-cgroup-control-group 
 - **Docker Host**
 - **Dockerfile**

   A **Dockerfile** is a text document that contains all the commands or instructions to bulid an image automatically by reading.

<img width="1146" height="722" alt="{FB54CE70-FD4E-4313-9563-AD3C0E40F078}" src="https://github.com/user-attachments/assets/5b778e65-d46b-45e7-9b5c-8d41ce04e2a2" />

 - Docker Registry
 - Docker Images
 - Docker containers
 - Docker Composer
<img width="3200" height="2400" alt="image" src="https://github.com/user-attachments/assets/473fb432-24db-446b-b878-a22efd51f077" />

### 🔥Container Application Deployment Steps on Docker

![image](https://github.com/user-attachments/assets/3533c007-57de-41ac-8d92-42006c4f96ee)




#### ✅Explain Basic Docker Usage Workflow

   - **🎯1.**	Everything starts with the Dockerfile. The Dockerfile is the source code of the Image.

   - **🎯2.**	Once the Dockerfile is created, you build it to create the image of the container. The image is just the "compiled version" of the "source code" which is the Dockerfile.

   - **🎯3.**	Once you have the image of the container, you should redistribute it using the registry. The registry is like a git repository -- you can push and pull images.

   - **🎯4.**	Next, you can use the image to run containers. A running container is very similar, in many aspects, to a virtual machine (but without the hypervisor).


https://media.licdn.com/dms/image/v2/D4D22AQEFrS_C9sqFDg/feedshare-shrink_800/B4DZiXMXEFGQAg-/0/1754883267161?e=1757548800&v=beta&t=EubqhNFUZyTl2i_Eb81Dq2hLIYUcDyxD4fwOJeCHclc
