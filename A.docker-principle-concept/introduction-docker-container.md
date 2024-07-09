### Technological Transformation

 - #### **Bare Metal**
   - Performance: Direct access to hardware, no virtualization overhead.
   - Control: Full control over the hardware and software stack.
   - Use Case: High-performance computing, gaming servers, financial trading systems.

 - #### **Key Reasons for Transition:**
   - **Bare Metal to Virtualization:** To improve resource utilization, flexibility, and isolation while maintaining control over the hardware.
   - **Virtualization to Cloud:** To leverage scalability, cost efficiency, reduced maintenance, and global accessibility, enabling faster innovation and business agility.
   - **Example:** Instead of having ten servers each running at 10% capacity, virtualization can consolidate them into one or two servers running at 80-90% capacity.


<p align="right">
<img src="https://github.com/saifulislam88/docker/assets/68442870/401f1965-77cb-450a-b558-5ad80b1428ea" alt="Technological Transformation" width="800"/>
</p>


### Virtualization


**Virtualization is software technology that separates physical infrastructures to create multiple virtual machine (VM) or virtual environments on a single server.**


This software technology of virtualization system is known as a virtual machine monitor (VMM) or virtual manager, which separates compute environments from the actual physical infrastructure–this makes it possible to run several operating systems on one computer at the same time. 
**A virtual machine monitor or VMM, also known as a hypervisor, is software that creates, runs and manage virtual machines (VMs).**



- Resource Utilization: Better utilization of physical hardware by running multiple VMs.
- Isolation: Strong isolation between applications.
- Flexibility: Easier to create, manage, and scale VMs.
- Use Case: Server consolidation, development and testing environments.


<p align="right">
<img src="https://github.com/saifulislam88/docker/assets/68442870/3c392818-aa43-4313-8893-72d83f1a5019" alt="Technological Transformation" width="800"/>
</p>


There are **two** main types of virtualization technology — 
 - **KVM Virtualization**
 - **OS Virtualization**

 
#### KVM Virtualization

**KVM (Kernel-Based Virtual Machine) Is An Open-Source Virtualization Technology That Allows You To Run Multiple Virtual Machines (VMs) On A Linux/Windows Host**. A Kernel-based Virtual Machine (KVM) allows you to turn Linux or Windows Server into a hypervisor, allowing your operating system to produce multiple virtual machines and isolated virtual environments.

- Type 1 - hypervisor is running on bare-metal hardware. Such hypervisors are VMWare ESXi, Linux KVM, Hyper-V
- Type 2 - hypervisor is running inside Host OS. Such hypervisors are VMWare Workstation are Oracle VirtualBox


##### KVM features
 - Security
 - Storage
 - Hardware support
 - Memory management
 - Live migration
 - Performance and scalability
 - Scheduling and resource control
 - Lower latency and higher prioritization


#### OS Virtualization

**একটি কার্নেলের ওপর একাধিক isolated ইউসার স্পেইসের অস্তিত্বকে অপারেটিং সিস্টেম লেভেল ভার্চুয়ালাইজেসন বলে.**
প্রতিটা ইউসার স্পেইসের রানটাইম এনভায়রনমেন্ট, ইউসার সেটিংস, ইত্যাদি ভিন্ন। আর একটা ইউসার স্পেইসের প্রসেস আরেকটা ইউসার স্পেইসে প্রবেশ করতে পারে না। মানে মেমোরি প্রটেকশন.

 - ##### Container

Let's revisit the different ways of deploying applications we talked about—locally, On-prem, and in the cloud. Imagine a friend, like another developer, wants to work with your code. They'd need to get their own "copy" of it. They'd go to a platform like GitHub and download your project files. Then, they'd install any extra tools needed to run your code smoothly. But sometimes, their computer might have different settings that make it hard for your code to work right. That's where containers come in handy. They wrap up your code with all the settings and tools it needs to run, no matter where it's put.
   - ###### **Defination**
      - **Containers are like pre-packaged sets of tools and code. You just plug them in, and they start working without any fuss.**
      - **Containers are predefined configurations and dependencies, along with the code files that make it possible for the code to run seamlessly.**
      - **একটা কার্নেলের ওপর আলাদা isolated ইউসার স্পেইসগুলোকে (User Space) কন্টেইনার (Container)বলা হয়.**
      - **Container is Runnable instance of the image, basically it is an isolated process.**
      - **Container is package of software that includes all dependencies: code, runtime, configuration, and system libraries so that it can run on any host system.**

- #### LXC


### Cloud Computing


- Scalability: On-demand resource allocation, easy to scale up or down.
- Cost Efficiency: Pay-as-you-go model, no need for upfront hardware investment.
- Maintenance: Reduced operational overhead as the cloud provider manages the infrastructure.
- Accessibility: Access from anywhere, ideal for remote work and distributed teams.
- Use Case: Web applications, SaaS, startups, dynamic workloads.


###
