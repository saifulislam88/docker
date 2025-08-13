##### 📌 The instructions/Command list in Dockerfile

- [FROM](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/G.Dockerfile-Instructions-Commands.md#-from)
- [WORKDIR](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/G.Dockerfile-Instructions-Commands.md#workdir)
- [USER](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/G.Dockerfile-Instructions-Commands.md#user)
- [MAINTAINER](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/G.Dockerfile-Instructions-Commands.md#maintainer)
- [LABEL](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/G.Dockerfile-Instructions-Commands.md#label)
- [COPY and ADD](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/G.Dockerfile-Instructions-Commands.md#copy-and-add)
- [RUN | CMD | ENTRYPOINT](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/G.Dockerfile-Instructions-Commands.md#run--cmd--entrypoint)
- [EXPOSE](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/G.Dockerfile-Instructions-Commands.md#expose)
- [VOLUME](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/G.Dockerfile-Instructions-Commands.md#volume)

 ###### ✅ **FROM**
 **Instruction creates the base image layer from base a image**.In every valid Dockerfile, FROM is the first instruction.

  &nbsp;&nbsp; **Example:**

```sh
FROM alpine:latest
FROM node:14
FROM python:3.8-slim
FROM ubuntu:20.04
```

###### ✅**WORKDIR**
Sets the working directory for any `RUN`, `CMD`, `ENTRYPOINT`, `COPY`, and `ADD` instructions that follow it in the Dockerfile.If you set `WORKDIR` multiple times, each `WORKDIR` instruction will override the previous one.

   &nbsp;&nbsp; **Example:**
```sh
# Set the working directory to /app
WORKDIR /usr/src/app

# Change working directory to /usr/src/app
WORKDIR /app

# Change working directory back to /app
WORKDIR /usr/src/app

```

###### ✅**USER**
Sets the user name (or UID) and optionally the user group (or GID) to use when running the image and for any `RUN`, `CMD`, and `ENTRYPOINT` instructions that follow it in the Dockerfile.

```sh
USER appuser
```
###### ✅**MAINTAINER**
The MAINTAINER instruction was used in older versions of Docker to specify the person responsible for the Dockerfile or image.Metadata of the owner who owns the image

```sh
MAINTAINER Saiful Islam <saiful.islam@example.com>
```
###### ✅**LABEL**

The `LABEL` instruction is used to add metadata to an image. It is more versatile and can be used to specify the maintainer along with other metadata like version, description, and more.

```sh
LABEL maintainer="Saiful Islam <saiful.islam@example.com>"
LABEL version="1.0"
LABEL description="A simple nodejs application"
```

###### ✅**COPY and ADD**
In Dockerfiles, both the `COPY` and `ADD` instructions are used to copy files and directories from the host machine into the Docker image. However, there are some key differences between the two:


  - 🎯**COPY**
Only copies files and directories. It doesn't have additional capabilities like extracting archives.`COPY` is preferred for copying files and directories because it is simple and predictable.

```sh
# Set the working directory to /app
WORKDIR /app

# Copy local source code to /app using COPY
COPY . .

# OR We can copy local source code to /app using COPY
COPY . /app
COPY requirements.txt ./
```

   - 🎯**ADD**

**The `ADD` instruction is similar to COPY but with some additional features**. `ADD` is useful for specific cases where you need **to extract archives or download files from URLs**. If the source is a local tar archive (`e.g., a .tar, .tar.gz, .tar.bz2, etc.`), it will be automatically unpacked at the destination. Can add files from remote URLs. If the source is a URL, ADD downloads the file from the URL and adds it to the destination path.

```sh
# Set the working directory to /app
WORKDIR /app
ADD . /app
ADD app.tar.gz /app

# Download a file from a URL and add it to the /app directory
ADD https://example.com/somefile.tar.gz /app/
ADD https://example.com/somefile.txt /app/
```

##### **✅RUN | CMD | ENTRYPOINT**

In a Dockerfile, RUN, CMD, and ENTRYPOINT are instructions used to define commands that should be run in the container. They have distinct purposes and behaviors. Additionally, each of these instructions can be specified in either **`shell` form** or **`exec` form**. That means, there are two ways to specify the command to run. `RUN` `CMD` `ENTRYPOINT` supports both form.

**Shell form** 
The command is run inside a new shell process, which, by default, is /bin/sh -c on Linux and cmd /S /C on Windows. Each command runs in a shell (/bin/sh -c), which might not exist in some minimal base images.

```sh
# Example of writing in Dockerfile
RUN apt-get update && apt-get install -y python3
CMD python app.py
ENTRYPOINT python app.py
```

**Exec form**
This command is not run inside a new shell process. The exec form uses a JSON array and does not invoke a shell unless explicitly done.


```sh
# Example of writing in Dockerfile
RUN ["apt-get", "update"]
CMD ["python", "app.py"]
ENTRYPOINT ["python", "app.py"]
```


🎯- **RUN**

**RUN** command is mainly used to install a new software packages and applications on top of an existing image layer `[FROM ubuntu: latest]` in Dockerfile. When you use the `RUN` command, it will execute the instruction and will create a new layer.

**Example from `Shell` form**

```sh
RUN apt-get -y update
RUN apt-get install vim && apt-get install -y libpq-dev
```

**Example from `Exec` form**

```sh
RUN ["apt-get", "update"]
RUN ["apt-get", "install", "vim"]
```


🎯- **CMD**

**CMD** in Dockerfile Instruction is used to execute a command in running container, **there should be one CMD in a Dockerfile.**
CMD executes the **final** commands when you launch a new container from image and also we use CMD command to provide default values of an executing container. **In a Dockerfile, if we include multiple CMD commands, then only the last instruction is used.**

```sh
FROM python:3.8-slim

# Set the working directory
WORKDIR /app

# Copy the application files
COPY . /app

# Install dependencies
RUN pip install -r requirements.txt

# Set the entrypoint
ENTRYPOINT ["python"]

# Set the default command arguments
CMD ["app.py"]

```
This **CMD** sets the default command to run **python app.py** when the container starts. That means python app.py parameters will be **ENTRYPOINT**



🎯- **ENTRYPOINT**

The ENTRYPOINT instruction defines the command that will always be run, while CMD provides the default arguments for that command. However, if you specify both CMD and ENTRYPOINT with the same command, it can lead to unintended behavior.


```sh
FROM python:3.8-slim

# Set the working directory
WORKDIR /app

# Copy the application files
COPY . /app

# Install dependencies
RUN pip install -r requirements.txt

# Set the entrypoint to python
ENTRYPOINT ["python"]

# Set the default command to app.py
CMD ["app.py"]

```
**Explanation:**

The **ENTRYPOINT** specifies **python** as the executable. The CMD provides **app.py** as the default argument. When running the container, the default command will be **python app.py**. If both `CMD` and `ENTRYPOINT` specify the same command, it can lead to repeated commands and unintended behavior. For example:

```sh
ENTRYPOINT ["python", "app.py"]
CMD ["python", "app.py"]
```

###### ✅**EXPOSE**

Make port 80 available to the world outside this container

`EXPOSE 80`

###### ✅**VOLUME**

Create a volume at /data

`VOLUME ["/data"]`
