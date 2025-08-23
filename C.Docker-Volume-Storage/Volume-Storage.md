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


#### RabbitMQ Managemnet
- Use only one Volumes
```sh
docker run -d --name rabbitmq-prod --hostname rabbitmq-prod -v rabbitmq_data:/var/lib/rabbitmq --restart unless-stopped -p 5672:5672 -p 15672:15672 rabbitmq:management
```

- Use Two Separate Volumes
```sh
docker run -d --name rabbitmq-prod --hostname rabbitmq-prod -v rabbitmq-data:/var/lib/rabbitmq -v rabbitmq-config:/etc/rabbitmq --restart unless-stopped -p 5672:5672 -p 15672:15672 rabbitmq:management
```
```sh
docker exec -it rabbitmq-prod rabbitmqctl list_users
docker exec -it rabbitmq-prod rabbitmqctl list_queues
docker cp /home/saiful/txt.log rabbitmq-prod:/var/lib/rabbitmq
```
```sh
docker stop rabbitmq-prod 
docker rm rabbitmq-prod
```

#### MySQL | Redis | Nginx

```sh
docker run -d --name mysql-db -v mysql-data:/var/lib/mysql -v mysql-config:/etc/mysql -e MYSQL_ROOT_PASSWORD=secret mysql:8
```
```sh
docker run -d --name redis-cache -v redis-data:/data -v redis-config:/usr/local/etc/redis redis:7
```
```sh
docker run -d --name nginx-web -v nginx-config:/etc/nginx -v nginx-html:/usr/share/nginx/html -p 80:80 nginx:alpine
```
---

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


### 🔁 1. Node.js Web App with Secure Upload Folder

**Use case**: Uploaded files are processed immediately and shouldn’t persist on disk.

```bash
docker run -d --name node-app \
  --tmpfs /app/uploads:rw,size=64m \
  -v app-code:/app \
  node:18
```

✅ **Benefit**: Prevents sensitive user uploads from being written to disk.

---

### 🔐 2. Python App with Secrets in Memory

**Use case**: Load secrets into a mounted tmpfs directory that gets cleared on reboot.

```bash
docker run -d --name secure-py \
  --tmpfs /run/secrets:rw,size=1m \
  -v pycode:/app \
  python:3.11
```

✅ **Benefit**: Keeps credentials out of persistent storage and logs.

---

### ⚡ 3. Java Application with In-Memory Temp Storage

**Use case**: Java apps often use `/tmp` for intermediate processing (sorting, zipping).

```bash
docker run -d --name java-api \
  --tmpfs /tmp:rw,size=200m \
  -v javacode:/app \
  openjdk:17
```

✅ **Benefit**: High-speed access for temporary files during runtime.

---

### 🧪 4. CI/CD Pipeline Container (GitLab Runner)

**Use case**: Mount `/build` or `/cache` directories into memory to speed up builds/tests.

```bash
docker run -d --name ci-runner \
  --tmpfs /build:rw,size=512m \
  -v ci-repo:/repo \
  alpine:latest sh -c "build.sh"
```

✅ **Benefit**: Reduces disk I/O and avoids persisting intermediate builds.

---

### 🖥️ 5. Nginx Reverse Proxy with Memory-based Session Storage

**Use case**: Cache session data or client upload buffers temporarily in RAM.

```bash
docker run -d --name nginx-secure \
  --tmpfs /var/lib/nginx/body:rw,size=100m \
  -v nginx-conf:/etc/nginx \
  nginx:latest
```

✅ **Benefit**: Speeds up large uploads and avoids disk writes.

---

### ✅ Best Practices Recap

| Use Case             | `--tmpfs` Mount Path       | Reason                                 |
|----------------------|----------------------------|----------------------------------------|
| User uploads         | `/app/uploads`             | Avoid storing sensitive files on disk  |
| Secrets              | `/run/secrets`             | Prevent secrets leakage to volume      |
| Temp file ops        | `/tmp`                     | High I/O during sort/build             |
| Build cache          | `/build`                   | CI/CD speedup                          |
| Session storage      | `/var/lib/nginx/body`      | Secure large client requests           



### When to Use:

**Volumes:** For data that needs to persist across container restarts.\
**Bind Mounts:** When you need to access or modify files on the host system.\
**tmpfs:** For temporary or secure data storage that doesn’t need persistence.

**Key Benefits of Volumes:**

Easy backup, restore, and migration.\
Better performance (especially with databases).\
Isolation from container lifecycle.




![image](https://github.com/saifulislam88/docker/assets/68442870/0e56ca7a-8b0e-455b-8b8e-ae92660e00e4)
