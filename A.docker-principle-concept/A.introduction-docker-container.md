## **Docker Container Administration | An Introduction & Principle Concept**<br>

<img src="https://github.com/saifulislam88/docker/assets/68442870/09012688-7671-4f50-8208-dedad3b66353" alt="Signature" width="400"/>

&nbsp;&nbsp;**Copyright** © 2024 Md. Saiful Islam(**mSI**). All Rights Reserved | **Internet & ChatBot**<br>
<br>
## &nbsp;&nbsp;**Table of Contents**
- [Technological Transformation](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/A.introduction-docker-container.md#technological-transformation---bare-metal---virtualization--container--cloud)
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

### 🚀 **Virtualization**

**Virtualization is software technology that separates physical infrastructures to create multiple virtual machines (VMs) or virtual environments on a single server.**

This software technology of virtualization system is known as a virtual machine monitor (VMM) or virtual manager, which separates compute environments from the actual physical infrastructure–this makes it possible to run several operating systems on one computer at the same time. 
**A virtual machine monitor or VMM, also known as a hypervisor, is software that creates, runs, and manages virtual machines (VMs).**

  - #### 🔥 **Virtualization Features**

     - **Resource Utilization:** Better utilization of physical hardware by running multiple VMs.
     - **Isolation:** Strong isolation between virtual environments and applications.
     - **Flexibility:** Easier to create, snapshot, manage, clone, and scale VMs.
     - **Use Case:** Server consolidation, legacy software support, cloud computing, development, and testing environments.

<p align="right">
<img src="https://github.com/saifulislam88/docker/assets/68442870/3c392818-aa43-4313-8893-72d83f1a5019" alt="Technological Transformation" width="800"/>
</p>

  - #### 🔥 **Types of Virtualization Technologies**
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;There are **two** main types of virtualization technologies:<br>
 
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 🛠️ **Hardware-level Virtualization | Virtual Machine (VM)**\
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 🛠️ **OS-level Virtualization | Container**

---

### 🚀 **Hardware-level Virtualization (Hypervisors)**

**Hardware virtualization uses a Hypervisor to emulate underlying hardware, allowing multiple full Operating Systems (Guest OS) to run independently on a single physical host.** Hypervisors are categorized into two distinct types based on where they reside in the system stack:

🛠️ **Type 1 - Hypervisor (Bare-Metal):** Runs directly on the host machine's physical hardware without an underlying host operating system. It offers enterprise-grade performance and efficiency.
*   **Linux KVM:** Built directly into the Linux Kernel, turning Linux into a Type-1 hypervisor.
*   **VMware ESXi:** Enterprise bare-metal hypervisor managed via vSphere.
*   **Microsoft Hyper-V:** Microsoft's native hypervisor architecture for Windows Server.
*   **Xen Project / XCP-ng:** Highly secure open-source bare-metal microkernel hypervisor.
*   **Nutanix AHV:** Acropolis Hypervisor built for hyperconverged infrastructure.

🛠️ **Type 2 - Hypervisor (Hosted):** Runs as a software application inside a standard Host Operating System (like Windows, macOS, or Linux). Ideal for local testing and developer environments.
*   **VMware Workstation Pro / Player:** Premium desktop virtualization for Windows and Linux.
*   **Oracle VirtualBox:** Free and open-source cross-platform virtualizer.
*   **VMware Fusion:** Desktop virtualization specifically built for macOS users.
*   **Parallels Desktop:** Ultra-fast desktop virtualization for running Windows on Apple Silicon Macs.
*   **QEMU:** A powerful open-source machine emulator and virtualizer.

---

### 🚀 **Linux KVM (Kernel-Based Virtual Machine)**

**KVM (Kernel-Based Virtual Machine) is an open-source virtualization technology built exclusively for the Linux Kernel.** It turns a Linux host into a powerful Type-1 hypervisor, allowing the host kernel to act as a virtual machine monitor. KVM relies on QEMU for complete hardware/device emulation to produce high-performance, isolated virtual machines.

*(Note: KVM is native to Linux and cannot be run on a Windows Host; Windows relies on its own hypervisor, Hyper-V).*

![image_resized_for_md](https://github.com/user-attachments/assets/bf1e5dae-6f4c-4789-8ce0-99e505726ef3)

  - #### 🔥 **KVM Core Features**
     - **Security:** Leverages Linux security components like SELinux and sVirt for advanced VM isolation.
     - **Storage:** Supports a wide range of storage types including local disks, NAS, SAN, and distributed filesystems (Ceph, GlusterFS).
     - **Hardware Support:** Automatically supports any hardware that is compatible with the underlying Linux Kernel.
     - **Memory Management:** Inherits Linux memory management features such as NUMA, Huge Pages, and Kernel Same-page Merging (KSM).
     - **Live Migration:** Allows moving running virtual machines between physical hosts without any downtime.
     - **Performance and Scalability:** Achieves near-native bare-metal speed by executing guest code directly on the host CPU.

---

### 🚀 **OS-level Virtualization (Containers)**

**OS-level virtualization isolates user spaces by sharing the host operating system's single kernel instead of simulating virtual hardware.** It deploys highly lightweight, fast, and resource-efficient environments called Containers.

🛠️ **Container Runtimes and Orchestrators:**
*   **Docker:** The world's most popular open-source platform for containerization.




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
       - runc | Use `runc` Directly (Advanced Only)
          - `runc` is what actually starts containers | runc run `mycontainerid`
          - No Docker, no containerd — but very manual, Handle networking and volumes yourself, Manually create rootfs, Write your own config.json

[More Details](https://www.linkedin.com/posts/mmumshad_kodekloud-devops-kubernetes-activity-7153377989160751105-viax/?utm_source=share&utm_medium=member_desktop)






