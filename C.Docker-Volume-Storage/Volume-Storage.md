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
