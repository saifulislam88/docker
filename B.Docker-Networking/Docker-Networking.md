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

