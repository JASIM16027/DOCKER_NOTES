# Docker Notes

## Operating System

### What is an operating system?
- An operating system (OS) is software that manages computer hardware resources and provides services for computer programs.
- It acts as an intermediary between the hardware and software, allowing applications to run efficiently and enabling users to interact with the computer.

### RAM, Hard Disk, Processor
- **RAM (Random Access Memory):** Temporary storage for data and instructions the CPU needs to access quickly.
- **Hard Disk:** Non-volatile storage device for long-term data storage on magnetic or solid-state drives.
- **Processor (CPU):** The brain of the computer, performing calculations and executing instructions.

### How is software installed on a computer?
- Software installation involves copying files from a storage medium (e.g., CD, USB drive) to the hard disk.
- The installation process sets up the necessary files and configurations for the software to be executed.

### How does the software load in RAM?
- When a program is executed, the OS loads the necessary parts of the software from the hard disk into RAM.
- The instructions and data reside in RAM during execution, allowing the CPU to access them quickly.

### 32-bit and 64-bit Computers
- **32-bit:** Processes data in 32-bit chunks, limited to 4 GB of RAM.
- **64-bit:** Processes data in 64-bit chunks, capable of handling more RAM, improving performance for larger applications.

## Processor

![image](https://github.com/JASIM16027/DOCKER_NOTE/assets/39296494/2c03909d-db29-40dc-8be5-19d8c77a3fa2)


### Register Set
- A small amount of very fast memory within the CPU.
- Holds data that the CPU is currently working on or needs frequently.
- Examples: AX, BX, CX registers.

### Pointing Register
- A register that holds memory addresses.
- Used to point to specific locations in memory for data retrieval or storage.

### Arithmetic and Logical Operations
- Processors support operations like AND, OR, NOT, ADD, SUB, MUL, and DIV.

## Process (Virtual Computer)

![image](https://github.com/JASIM16027/Docker_Notes/assets/39296494/f6e26763-5def-4583-9aae-8a6e8e8cffb2)


### Process State
- A process is an instance of a running program.
- States include running, waiting, or terminated.

### Process ID (PID)
- Unique identifier assigned by the OS to each process.

### Attributes of a Process
- Attributes include total read/write operations, priority level, and other characteristics.

### Context Switching
- The process of saving and restoring the state of a process, allowing the CPU to switch between processes.
- 

### Process Control Block (PCB)
- A data structure maintained by the OS for each process.
- Contains information like current state, CPU registers, memory allocation, and more.

### Concurrency
- The ability of multiple processes or threads to execute in overlapping time intervals, giving the illusion of simultaneous execution.

### Multi-threaded/Core Processor
- A CPU with multiple cores, allowing it to execute multiple threads simultaneously for improved performance.

### Logical CPU or Processor
- The virtual representation of a CPU core, allowing systems with hyper-threading or multi-threading technology to divide each physical core into multiple logical CPUs.

### Parallel Execution
- Simultaneous execution of multiple tasks or processes on different processors or cores, enhancing performance and efficiency.

### Thread or Virtual Process
- A unit of execution within a process, sharing the same memory space for concurrent execution.
- Threads also undergo context switching.

- ``` When the computer starts, the operating system's code is executed, and the processor only knows the operating system. ```
### Introduction to Docker and Its Ecosystem

#### Background: Virtualization Before Docker

![image](https://github.com/JASIM16027/DOCKER_NOTE/assets/39296494/10074293-35ae-4aca-afe0-f71204cfa1b6)


**Hypervisors:**
- Hypervisors are software, firmware, or hardware that create and manage virtual machines (VMs).
- They allow multiple VMs to run on a single physical machine by virtualizing the underlying hardware.
- Each VM runs a full operating system and requires dedicated resources, such as CPU, memory, and storage.

**Limitations of Hypervisors:**
- VMs are resource-intensive since each VM requires its own OS.
- VMs have longer startup times due to the need to boot an entire OS.
- Managing and maintaining multiple VMs can be complex and inefficient.

### Docker: A Solution to Traditional Virtualization Limitations

**Why Do We Need Docker?**
- **Lightweight:** Docker containers share the host OS kernel, reducing the overhead associated with running multiple OS instances.
- **Isolated:** Containers provide process and filesystem isolation, ensuring applications run in their own environments.
- **Fast Startup Times:** Containers can start almost instantly because they don't require booting a full OS.
- **Efficient Resource Usage:** Containers use fewer resources compared to VMs, as they share the host OS kernel and other resources.

### What is Docker?

Docker is a platform and ecosystem designed to develop, ship, and run applications inside containers. It consists of several key components that work together to manage containerized applications efficiently.


### Container Management:
- **docker run**: Create and start a new container from an image.
- **docker start**: Start one or more stopped containers.
- **docker stop**: Stop one or more running containers.
- **docker restart**: Restart one or more containers.
- **docker rm**: Remove one or more containers.
- **docker ps**: List running containers.
- **docker ps -a**: List all containers (including stopped ones).
- **docker exec**: Run a command inside a running container.
- **docker logs**: Fetch the logs of a container.

### Image Management:
- **docker build**: Build a Docker image from a Dockerfile.
- **docker pull**: Pull an image or a repository from a registry.
- **docker push**: Push an image or a repository to a registry.
- **docker images**: List all locally available images.
- **docker rmi**: Remove one or more images.
- **docker tag**: Tag an image with a new name and/or tag.

### Network Management:
- **docker network create**: Create a new Docker network.
- **docker network ls**: List Docker networks.
- **docker network inspect**: Display detailed information on one or more networks.
- **docker network connect**: Connect a container to a network.
- **docker network disconnect**: Disconnect a container from a network.

### Volume Management:
- **docker volume create**: Create a new volume.
- **docker volume ls**: List Docker volumes.
- **docker volume inspect**: Display detailed information on one or more volumes.
- **docker volume rm**: Remove one or more volumes.
- **docker volume prune**: Remove all unused volumes.

### System Management:
- **docker info**: Display system-wide information.
- **docker version**: Show the Docker version information.
- **docker system df**: Show Docker disk usage.
- **docker system prune**: Remove unused data (containers, networks, images, volumes).
- **docker stats**: Display a live stream of container resource usage statistics.

### Registry Management:
- **docker login**: Log in to a Docker registry.
- **docker logout**: Log out from a Docker registry.
- **docker search**: Search for Docker images on Docker Hub.
- 

#### Components of the Docker Ecosystem

1. **Docker Client:**
   - The Docker client is a command-line interface (CLI) tool used to interact with the Docker daemon.
   - Commands issued through the CLI (e.g., `docker run`, `docker build`) are sent to the Docker daemon for execution.

2. **Docker Server (Docker Daemon):**
   - The Docker daemon (`dockerd`) runs on the host machine and manages Docker objects such as images, containers, networks, and volumes.
   - It listens for Docker API requests and handles the creation, execution, and monitoring of containers.

3. **Docker Machine:**
   - Docker Machine is a tool that simplifies the setup of Docker on virtual machines or physical hosts.
   - It automates the provisioning and configuration of Docker hosts, making it easier to manage Docker environments across different platforms.

4. **Docker Images:**
   - Docker images are read-only templates that contain the application code, runtime, libraries, and dependencies required to run an application.
   - Images are built from Dockerfiles, which specify the instructions needed to create the image.
   - They are used to instantiate Docker containers.

5. **Docker Hub:**
   - Docker Hub is a cloud-based registry service for sharing and accessing Docker images.
   - It allows users to publish their own images, browse existing images, and download images for use in their own environments.

6. **Docker Compose:**
   - Docker Compose is a tool for defining and running multi-container Docker applications.
   - Using a YAML file (`docker-compose.yml`), you can specify the services, networks, and volumes needed for an application.
   - It simplifies the management of applications that require multiple containers working together.

### Step-by-Step Explanation of Docker's Functionality


1. **Building an Image:**
   - Create a `Dockerfile` with instructions on how to build your application image.
   - Use the command `docker build -t <image_name> .` to build the image from the Dockerfile.

2. **Running a Container:**
   - Use the command `docker run -d --name <container_name> <image_name>` to run a container from an image.
   - The `-d` flag runs the container in detached mode, allowing it to run in the background.

3. **Managing Containers:**
   - Use `docker ps` to list running containers.
   - Use `docker stop <container_name>` to stop a running container.
   - Use `docker rm <container_name>` to remove a stopped container.

4. **Using Docker Compose:**
   - Create a `docker-compose.yml` file to define your multi-container application.
   - Use the command `docker-compose up -d` to start the application with all defined services.
   - Use `docker-compose down` to stop and remove the application’s containers, networks, and volumes.

     

## Dockerfile

```

FROM node:18-alpine

WORKDIR /usr/src/app

COPY package*.json ./

RUN npm ci

COPY . .

RUN npm run build

CMD [ "node", "dist/main.js" ]


```


This is a Dockerfile, a script that defines the environment and steps needed to create a Docker container for a Node.js application. Let's go through it step-by-step:

1. **FROM node:18-alpine**
   - This line specifies the base image for the Docker container. `node:18-alpine` is a lightweight version of the Node.js 18 runtime, based on the Alpine Linux distribution. This helps keep the image small and efficient.

2. **WORKDIR /usr/src/app**
   - This sets the working directory inside the container to `/usr/src/app`. All subsequent commands will be run in this directory. If the directory does not exist, it will be created.

3. **COPY package*.json ./**
   - This command copies the `package.json` and `package-lock.json` files from the host machine to the current working directory in the container (`/usr/src/app`). The `*` wildcard ensures both files are copied if they exist.

4. **RUN npm ci**
   - `npm ci` (short for "clean install") installs the dependencies listed in `package-lock.json`. This command is preferred in CI (Continuous Integration) environments as it ensures a clean and reproducible install of dependencies.

5. **COPY . .**
   - This copies all files from the current directory on the host machine to the current working directory in the container (`/usr/src/app`). Essentially, it adds the application code to the container.

6. **RUN npm run build**
   - This runs the `build` script defined in the `package.json` file. This script typically compiles the application, preparing it for production. The exact behavior depends on what is defined in the `build` script of your `package.json`.

7. **CMD [ "node", "dist/main.js" ]**
   - This specifies the command to run when the container starts. Here, it runs `node dist/main.js`, which likely starts the Node.js application. `dist/main.js` is presumably the entry point of the built application.

## Docker Compose configuration for a microservices architecture:

version: '3.8'
```
services:
  user-service:
    container_name: user-service
    build:
      context: ./user-service
      dockerfile: Dockerfile
    ports:
      - "8081:8081"
    env_file:
      - ./user-service/.env
    networks:
      - my-network

  product-service:
    container_name: product-service
    build:
      context: ./product-service
      dockerfile: Dockerfile
    ports:
      - "8082:8082"
    env_file:
      - ./product-service/.env
    networks:
      - my-network

  order-service:
    container_name: order-service
    build:
      context: ./order-service
      dockerfile: Dockerfile
    ports:
      - "8083:8083"
    env_file:
      - ./order-service/.env
    networks:
      - my-network

networks:
  my-network:
    driver: bridge

```

### Conclusion

Docker revolutionizes the way applications are developed, shipped, and run by providing a lightweight, efficient, and consistent environment for application execution. Its ecosystem, comprising various tools and services, enhances the capabilities of container management, making it a powerful solution for modern application development and deployment.


## Docker

### Before Docker - Hypervisor
- Hypervisors create and manage virtual machines (VMs) that emulate entire computer systems, running full operating systems and requiring dedicated resources.

### Hypervisor vs Docker
- Hypervisors virtualize hardware to run multiple VMs on a single machine.
- Docker virtualizes the OS, allowing containers to share the host OS kernel, making them more lightweight.

### Why do we need Docker?
- Docker provides lightweight, isolated containers with faster startup times, using fewer resources, and allowing efficient packaging and deployment of applications.

### What is Docker? All parts of the Docker ecosystem.
- Docker is a platform for creating and managing containers.
- Components: Docker client (CLI), Docker server (daemon), Docker machine, Docker images, Docker Hub, Docker Compose.

### Workflow of Docker: "docker run -it <some-image>" - explained
1. Execute `docker run -it <some-image>` in the terminal.
2. Docker CLI validates and sends the command to the Docker server.
3. Docker server pulls the image from Docker Hub if not available locally.
4. Docker server creates a container based on the image.
5. The `-it` option makes the container run in interactive mode, providing a shell prompt for interaction.
6. User interacts with the container via the command prompt.

### Docker Image and its parts
- A Docker image is a snapshot of a file system containing software, dependencies, and configurations.
- Consists of a file system snapshot and a startup command.

### "username@machineName:/$" - explained
- The command prompt inside the Docker container:
  - `username`: User within the container.
  - `machineName`: Container's virtual machine or host system name.
  - `/$`: Current working directory inside the container.

### Kernel, Namespacing, and Control Groups
- **Kernel:** Core of the OS interacting with hardware and providing essential services.
- **Namespacing:** Linux kernel feature for resource isolation and process-level virtualization.
- **Control Groups (cgroups):** Kernel feature managing and limiting resources available to processes within a container.

### What is a Container? (Virtual Computer)
- A lightweight, isolated runtime environment encapsulating an application and its dependencies.
- Shares the host OS kernel but has its own isolated file system and resources.

### How do Windows and Mac have Containers without Namespacing?
- Use virtualization technologies (Hyper-V for Windows, HyperKit for Mac) to create lightweight VMs running a Linux distribution (WSL for Windows).
- Containers are deployed within these VMs, providing an isolated runtime environment.

### Docker Client & Server
- **Docker Client:** CLI tool for interacting with Docker.
- **Docker Server (Daemon):** Manages containers, handles image operations, and communicates with the host OS, similar to an OS for Docker machines.

### How to install images from Docker Hub
- Use `docker pull <image-name>` to install an image from Docker Hub.

### Set default command within Docker image
- Use the `CMD` instruction in a Dockerfile to set a default command to be executed when starting a container.

### Checking container status
- Use `docker ps` to check the status of running containers, providing information like container ID, image, command, created time, status, and names.

### Remove command for unused containers
- Use `docker rm <container-id>` to remove unused containers.
- Use `docker system prune` to remove all stopped containers, unused networks, dangling images, and build cache.

### Difference between `docker kill` and `docker rm` command
- `docker kill`: Sends a termination signal to a running container, forcing it to stop immediately.
- `docker rm`: Removes a stopped container from the system.

### "bin" folder with each image
- Contains binary executable files for commands and utilities included in the image.

### Install Ubuntu image and explore Linux commands
- Install the Ubuntu image with `docker pull ubuntu`.
- Run a container from the image using `docker run -it ubuntu`.
- Explore and execute Linux commands inside the container, such as `ls`, `cd`, `pwd`, etc.

### Difference between host/normal user and root user
- **Normal User:** Limited permissions, cannot perform certain administrative tasks.
- **Root User:** Administrative privileges, can access and modify system files, install software, and make system-wide changes.
