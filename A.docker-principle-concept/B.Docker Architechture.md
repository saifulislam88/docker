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


#### ✅Explain Basic Docker Usage Workflow

   - **🎯1.**	Everything starts with the Dockerfile. The Dockerfile is the source code of the Image.

   - **🎯2.**	Once the Dockerfile is created, you build it to create the image of the container. The image is just the "compiled version" of the "source code" which is the Dockerfile.

   - **🎯3.**	Once you have the image of the container, you should redistribute it using the registry. The registry is like a git repository -- you can push and pull images.

   - **🎯4.**	Next, you can use the image to run containers. A running container is very similar, in many aspects, to a virtual machine (but without the hypervisor).
