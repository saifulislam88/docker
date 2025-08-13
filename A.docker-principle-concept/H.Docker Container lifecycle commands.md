##### 📌Manage Containers: Use Docker commands to manage the lifecycle of containers | Deploy Updates: Rebuild, retag, push updates, and restart the container to deploy updates

`docker ps -a`\
`docker start <container_name_or_id>`\
`docker stop <container_name_or_id>`\
docker restart <container_name_or_id>/
`docker rm <container_name_or_id>`/
`docker inspect <container_name_or_id>`/
`docker build -t <image_name>:<tag> .`/
`docker tag <old_image_name>:<old_tag> <new_image_name>:<new_tag>`/
`docker push <image_name>:<tag>`/
`docker pull <image_name>:<tag>`/
`docker rmi <image_name>:<tag>`/
`docker run -d --name <container_name> <image_name>:<tag>`/
`docker login`/
`docker tag <local_image_name>:<tag> username/my-app:<tag>`/
`docker push username/my-app:<tag>`

