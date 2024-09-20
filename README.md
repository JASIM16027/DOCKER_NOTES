# Docker Notes

## Operating System

### What is an operating system?
- An operating system (OS) is software that manages computer hardware resources and provides services for computer programs.
- It acts as an intermediary between the hardware and software, allowing applications to run efficiently and enabling users to interact with the computer.

- An operating system (OS) consists of two primary layers: the application layer and the kernel layer. Each layer has distinct responsibilities and interacts in specific ways to ensure the smooth functioning of the computer system.

### Application Layer
- **Role**: The application layer serves as the interface between the user and the operating system. It includes all the user-facing applications and utilities that perform various tasks.
- **Components**: This layer comprises software applications like web browsers, word processors, and media players, as well as system utilities that manage files, configure settings, and monitor system performance.
- **Functionality**: Applications in this layer rely on the underlying services provided by the kernel to perform their tasks. They request resources and services through system calls, which the kernel processes.
- **User Interaction**: This layer is where users interact directly with the system, entering commands and receiving outputs.

### Kernel Layer
- **Role**: The kernel is the core part of the operating system, acting as a bridge between the application layer and the hardware. It manages system resources and facilitates communication between hardware and software.
- **Components**: The kernel includes several critical components:
  - **Process Management**: Handles the creation, scheduling, and termination of processes, ensuring efficient CPU utilization.
  - **Memory Management**: Manages the allocation and deallocation of memory space to processes, and handles paging and segmentation.
  - **Device Management**: Controls hardware devices through device drivers, ensuring that applications can interact with hardware components like printers, disk drives, and network interfaces.
  - **File System Management**: Manages data storage, retrieval, and organization on storage devices, providing a structured way to store and access files.
  - **Security and Access Control**: Enforces security policies, controls access to system resources, and ensures that only authorized processes and users can perform certain actions.
- **Functionality**: The kernel operates in a privileged mode with full access to all hardware. It handles low-level tasks such as interrupt handling, context switching, and communication between hardware and software components.
- **Hardware Interaction**: It directly interacts with the hardware through device drivers, translating high-level commands from applications into low-level operations that the hardware can execute.

By maintaining a clear separation between these two layers, operating systems ensure that user applications can run efficiently and securely, while the kernel manages the underlying hardware complexities. This structure also allows for better stability and security, as the kernel can enforce strict access controls and manage system resources effectively.

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

![image](https://github.com/JASIM16027/Docker_Notes/assets/39296494/5f9559f1-483d-47a5-b633-c06c36de9b1c)


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

Got it! Here's the information organized into a table format with a sample command:

| Category            | Command                     | Description                                                  | Example                                              |
|---------------------|-----------------------------|--------------------------------------------------------------|------------------------------------------------------|
| Container Management| docker run                  | Create and start a new container from an image.              | `docker run -d --name my_container nginx`           |
|                     | docker start                | Start one or more stopped containers.                        | `docker start my_container`                         |
|                     | docker stop                 | Stop one or more running containers.                        | `docker stop my_container`                          |
|                     | docker restart              | Restart one or more containers.                              | `docker restart my_container`                       |
|                     | docker rm                   | Remove one or more containers.                               | `docker rm my_container`                            |
|                     | docker ps                   | List running containers.                                     | `docker ps`                                          |
|                     | docker ps -a                | List all containers (including stopped ones).                | `docker ps -a`                                       |
|                     | docker exec                 | Run a command inside a running container.                   | `docker exec -it my_container bash`                 |
|                     | docker logs                 | Fetch the logs of a container.                               | `docker logs my_container`                          |
| Image Management    | docker build                | Build a Docker image from a Dockerfile.                      | `docker build -t my_image .`                        |
|                     | docker pull                 | Pull an image or a repository from a registry.              | `docker pull nginx`                                 |
|                     | docker push                 | Push an image or a repository to a registry.                | `docker push my_username/my_image`                  |
|                     | docker images               | List all locally available images.                           | `docker images`                                     |
|                     | docker rmi                  | Remove one or more images.                                   | `docker rmi my_image`                               |
|                     | docker tag                  | Tag an image with a new name and/or tag.                    | `docker tag my_image my_new_image`                  |
| Network Management  | docker network create       | Create a new Docker network.                                 | `docker network create my_network`                  |
|                     | docker network ls           | List Docker networks.                                        | `docker network ls`                                 |
|                     | docker network inspect      | Display detailed information on one or more networks.        | `docker network inspect my_network`                 |
|                     | docker network connect      | Connect a container to a network.                            | `docker network connect my_network my_container`    |
|                     | docker network disconnect   | Disconnect a container from a network.                       | `docker network disconnect my_network my_container` |
| Volume Management   | docker volume create        | Create a new volume.                                         | `docker volume create my_volume`                    |
|                     | docker volume ls            | List Docker volumes.                                         | `docker volume ls`                                  |
|                     | docker volume inspect       | Display detailed information on one or more volumes.         | `docker volume inspect my_volume`                   |
|                     | docker volume rm            | Remove one or more volumes.                                  | `docker volume rm my_volume`                        |
|                     | docker volume prune         | Remove all unused volumes.                                   | `docker volume prune`                               |
| System Management   | docker info                 | Display system-wide information.                             | `docker info`                                       |
|                     | docker version              | Show the Docker version information.                         | `docker version`                                    |
|                     | docker system df            | Show Docker disk usage.                                      | `docker system df`                                  |
|                     | docker system prune         | Remove unused data (containers, networks, images, volumes). | `docker system prune`                               |
|                     | docker stats                | Display a live stream of container resource usage statistics.| `docker stats`                                      |
| Registry Management | docker login                | Log in to a Docker registry.                                 | `docker login`                                      |
|                     | docker logout               | Log out from a Docker registry.                              | `docker logout`                                     |
|                     | docker search               | Search for Docker images on Docker Hub.                      | `docker search nginx`                               |


Sure, here's the rewritten list of Docker networking commands:

**List available networks:**
```
docker network ls
```

**Remove one or more networks:**
```
docker network rm [network]
```

**Show information on one or more networks:**
```
docker network inspect [network]
```

**Connect a container to a network:**
```
docker network connect [network] [container]
```

**Disconnect a container from a network:**
```
docker network disconnect [network] [container]
```

Here's the list of Docker image-related commands:

**Create an image from a Dockerfile:**
```
docker build [dockerfile-path]
```

**Build an image from a Dockerfile located in the current directory:**
```
docker build .
```

**Create an image from a Dockerfile and tag it:**
```
docker build -t [name]:[tag] [dockerfile-path]
```

**Specify a file to build from:**
```
docker build -f [file-path]
```

**Pull an image from a registry:**
```
docker pull [image]
```

**Push an image to a registry:**
```
docker push [image]
```

**Create an image from a tarball:**
```
docker import [url/file]
```

**Create an image from a container:**
```
docker commit [container] [new-image]
```

**Tag an image:**
```
docker tag [image] [image]:[tag]
```

**Show all locally stored top-level images:**
```
docker images
```

**Show history for an image:**
```
docker history [image]
```

**Remove an image:**
```
docker rmi [image]
```

**Load an image from a tar archive or stdin:**
```
docker load --input [tar-file]
```

**Save an image to a tar archive file using Docker save command:**
```
docker save [image] > [tar-file]
```

**Remove unused images:**
```
docker image prune
```

Replace `[dockerfile-path]`, `[name]`, `[tag]`, `[file-path]`, `[image]`, `[url/file]`, `[container]`, and `[new-image]` with the appropriate values according to your use case.



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

  ![image](https://github.com/JASIM16027/Docker_Notes/assets/39296494/6182a53b-3f59-4a52-9cdd-552a6c155d72)

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

![image](https://github.com/JASIM16027/Docker_Notes/assets/39296494/a9200b60-3b37-4b0f-a4e6-9601515683b4)


When comparing Docker containers to virtual machines (VMs), it's essential to understand their fundamental differences, use cases, and advantages.

### Docker Containers

**Overview:**
- Docker is a platform that uses OS-level virtualization to deliver software in packages called containers.
- Containers share the host system's kernel but run in isolated user spaces.

**Advantages:**
1. **Lightweight:** Containers are more lightweight than VMs because they share the host OS kernel, resulting in less overhead.
2. **Performance:** Since they don't need a full OS to boot, containers can start up and shut down much faster than VMs.
3. **Portability:** Containers encapsulate all dependencies and configurations, making them highly portable across different environments.
4. **Resource Efficiency:** Containers use resources more efficiently due to shared OS components and reduced overhead.

**Use Cases:**
- Microservices architecture
- Continuous integration/continuous deployment (CI/CD) pipelines
- Running multiple applications on a single OS instance
- Development and testing environments

### Virtual Machines (VMs)

**Overview:**
- VMs run on a hypervisor, which is a software layer that allows multiple operating systems to share a single hardware host.
- Each VM includes a full operating system and emulated hardware.

**Advantages:**
1. **Isolation:** VMs offer complete isolation since each VM runs a full OS. This makes them suitable for running multiple, different OS environments on the same physical hardware.
2. **Compatibility:** VMs can run any operating system that the hypervisor supports, making them more versatile for running different OSes.
3. **Security:** The full isolation provided by VMs can be beneficial for security-sensitive applications.

**Use Cases:**
- Running multiple OS instances on a single hardware system
- Legacy application support
- Use cases requiring strong isolation between applications
- Testing and development across different OS environments

### Key Differences

1. **Boot Time:**
   - **Containers:** Seconds
   - **VMs:** Minutes

2. **Resource Utilization:**
   - **Containers:** More efficient, share the host OS kernel
   - **VMs:** Less efficient, each VM requires a full OS

3. **Isolation:**
   - **Containers:** Process-level isolation
   - **VMs:** Full OS-level isolation

4. **Portability:**
   - **Containers:** Highly portable, suitable for microservices
   - **VMs:** Less portable, more suited for running different OSes

### Choosing Between Docker and VMs

- **Use Docker if:**
  - You need a lightweight, fast, and portable solution.
  - Your applications are designed as microservices.
  - You require efficient use of system resources.
  - You need a streamlined development and deployment pipeline.

- **Use VMs if:**
  - You need strong isolation between applications.
  - You need to run different operating systems on the same hardware.
  - Your application requires a full OS environment.
  - You are dealing with legacy systems or applications.

In summary, Docker containers are optimal for scenarios where resource efficiency, fast deployment, and application portability are critical. In contrast, VMs are more suitable for situations requiring complete isolation and the ability to run different operating systems on the same hardware.




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


### Docker Port Forwarding

Each computer has its own localhost and ports. Docker containers, being virtual machines, also have their own localhost and ports. To access services running inside Docker containers from the host machine, you need to perform port forwarding.

#### Accessing a MySQL Container

To connect to a MySQL database running inside a Docker container, you must map a port on the host machine to the container's port. Here’s how to do it:

1. **Run the MySQL container with port forwarding:**
   ```bash
   docker run -p host_machine_port:container_port -e MYSQL_ROOT_PASSWORD=your_password mysql
   ```
   Example:
   ```bash
   docker run -p 4000:3306 -e MYSQL_ROOT_PASSWORD=123456 mysql
   ```

2. **Enter the running container:**
   ```bash
   docker exec -it <container_id> sh
   ```

3. **Access MySQL inside the container:**
   ```bash
   mysql -u <MYSQL_USER> -p
   ```

Now, you can connect to MySQL on `localhost:4000` from the host machine. Docker will forward the request to the container's port `3306`.

#### MongoDB

1. **Start the MongoDB container with port forwarding:**
   ```bash
   sudo docker run -dp 27017:27017 -v local-mongo:/data/db --name local-mongo --restart=always mongo
   ```

2. **Enter the MongoDB container:**
   ```bash
   sudo docker exec -it local-mongo sh
   ```

3. **Start the MongoDB shell:**
   ```bash
   mongo
   ```

#### Redis

1. **Stop Redis server:**
   ```bash
   /etc/init.d/redis-server stop
   ```

2. **Start Redis server:**
   ```bash
   /etc/init.d/redis-server start
   ```

3. **Restart Redis server:**
   ```bash
   /etc/init.d/redis-server restart
   ```

#### PostgreSQL

1. **Start the PostgreSQL container with port forwarding:**
   ```bash
   sudo docker run -p 4000:5432 -e POSTGRES_PASSWORD=123456 postgres
   ```

2. **Enter the PostgreSQL container:**
   ```bash
   sudo docker exec -it <container_id> sh
   ```

3. **Access PostgreSQL CLI:**
   ```bash
   psql -U postgres
   ```

4. **Create a database inside the container:**
   ```sql
   CREATE DATABASE mydatabase;
   ```

5. **Create a user with a password:**
   ```sql
   CREATE ROLE myuser WITH LOGIN PASSWORD 'mypassword';
   ```

6. **Grant privileges to the user on the database:**
   ```sql
   GRANT ALL PRIVILEGES ON DATABASE mydatabase TO myuser;
   ```

7. **Show all databases:**
   ```sql
   \l
   ```

8. **Connect to a specific database:**
   ```sql
   \c database_name
   ```

9. **Show all tables:**
   ```sql
   \dt
   ```

10. **Access a specific schema:**
    ```sql
    \dt schema_name.*
    ```

11. **Query a specific table:**
    ```sql
    SELECT * FROM <table_name>;
    ```

12. **Exit the CLI:**
    ```sql
    \q
    ```

By using these commands, you can manage port forwarding and access various database services running inside Docker containers from your host machine.



### Docker Port Forwarding and Volume Mapping

This guide provides instructions for running Docker containers with port forwarding and volume mapping.

#### Port Forwarding

To forward a port from your host machine to a Docker container, use the following command:

```bash
docker run -p host_machine_port:container_port image_name
```

**Example:** To run an Nginx container and forward port 3004 on the host machine to port 80 in the container:

```bash
docker run -p 3004:80 nginx
```

When you request `localhost:3004`, the host machine will forward the request to the Nginx container running on port 80.

#### Volume Mapping

Volume mapping allows you to share files between your host machine and a Docker container. Use the following command:

```bash
docker run -v host_machine_folder_path:container_folder_path image_name
```

**Example:** To run a MySQL container and map a host directory (`/my/host/data`) to the container's data directory (`/var/lib/mysql`):

```bash
docker run -v /my/host/data:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=123456 mysql
```

#### Combining Port Forwarding and Volume Mapping

You can combine port forwarding and volume mapping in one command:

```bash
docker run -p host_machine_port:container_port -v host_machine_folder_path:container_folder_path image_name
```

**Example:** To run a MySQL container, forward port 4000 on the host machine to port 3306 in the container, and map a host directory (`/my/host/data`) to the container's data directory (`/var/lib/mysql`):

```bash
docker run -p 4000:3306 -v /my/host/data:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=123456 mysql
```

With volume mapping, files created in the container will be visible in the mapped directory on the host machine. This allows for easy file sharing and persistent data storage between the host and the container.


### Dockerfile

```dockerfile
# Use the official Node.js image based on Alpine Linux
FROM node:alpine

# Set the working directory to /app
WORKDIR /app

# Copy package.json from the host into the container's working directory
COPY package.json .

# Install dependencies listed in package.json
RUN npm install

# Copy all the application files from the host into the container's working directory
COPY . .

# Define the default startup command
CMD ["npm", "run", "start"]
```

### Building the Docker Image

To build the Docker image, run the following command:

```bash
docker build -t example-image:v1 .
```

### How the Process Works

1. **FROM node:alpine:** The Docker daemon starts by creating a temporary container using the official Node.js image based on Alpine Linux.

2. **WORKDIR /app:** It then sets the working directory to `/app` within the container.

3. **COPY package.json .:** The `package.json` file from the host machine is copied into the container's `/app` directory.

4. **RUN npm install:** This command installs all the dependencies listed in `package.json` within the container.

5. **COPY . .:** All the application files from the host machine are copied into the container's working directory (`/app`).

6. **CMD ["npm", "run", "start"]:** This command specifies the default command to run when a container created from this image is started. It tells the container to start the Node.js application using `npm`.

### Pushing the Docker Image to Docker Hub

To share your Docker image with others, you can push it to a container registry like Docker Hub. Ensure you are logged in to your Docker Hub account using `docker login`.

1. **Tag the image with your username and version:**

   ```bash
   docker tag example-image:v1 your-username/example-image:v1
   ```

2. **Push the tagged image to Docker Hub:**

   ```bash
   docker push your-username/example-image:v1
   ```

### Summary

- **Build the Image:** The `docker build` command compiles the Dockerfile into an image.
- **FROM Directive:** Starts from a base image (Node.js based on Alpine Linux).
- **WORKDIR:** Sets the working directory in the container.
- **COPY:** Copies files from the host into the container.
- **RUN npm install:** Installs dependencies.
- **CMD:** Specifies the command to run the application.
- **Push to Docker Hub:** Tags and pushes the image to Docker Hub for sharing.



### 1. **What is the base image used in the Dockerfile?**

To find out the base image in a Dockerfile, inspect the `FROM` statement at the beginning of the file.

```bash
cat Dockerfile
```

The `FROM` statement specifies the base image being used.

---

### 2. **What command is used to run the application inside the container?**

The command used to run the application in a container is defined in the `CMD` or `ENTRYPOINT` section of the Dockerfile.

To inspect it:

```bash
cat Dockerfile
```

Look for the `CMD` or `ENTRYPOINT` instruction, which specifies how the application is launched.

---

### 3. **Build a Docker image using the Dockerfile and name it `webapp-color`.**

To build the Docker image from the Dockerfile, run the following command:

```bash
docker build -t webapp-color .
```

This command builds an image and names it `webapp-color` without specifying any tag, so it defaults to the `latest` tag.

---

### 4. **Run an instance of the image `webapp-color` and publish port 8080 on the container to 8282 on the host.**

To run the container, mapping the container's port 8080 to the host's port 8282:

```bash
docker run -d -p 8282:8080 webapp-color
```

This command runs the container in detached mode (`-d`), maps the container's port 8080 to host port 8282, and starts an instance of `webapp-color`.

---

### 5. **What is the base Operating System used by the `python:3.6` image?**

To find the base operating system of the `python:3.6` image, you can run a container interactively and check the OS details:

```bash
docker run -it python:3.6 /bin/bash
```

Inside the container, use the following command to check the operating system:

```bash
cat /etc/os-release
```

This will provide information about the base OS of the `python:3.6` image.

---

### 6. **Why use `-it` in the command `docker run -it python:3.6 /bin/bash`?**

The `-it` option in Docker is used to run a container interactively with a pseudo-TTY. Here's the breakdown:
- `-i` keeps STDIN open to interact with the container.
- `-t` allocates a pseudo-terminal.

The full command:

```bash
docker run -it python:3.6 /bin/bash
```

Allows you to interact with the container's shell directly.

---

### 7. **Build a smaller Docker image using the same Dockerfile and name it `webapp-color:lite`.**

To build a smaller image, modify the base image in the Dockerfile to something smaller like `python:3.6-alpine` and ensure that the final image size is under 150MB.

Here’s how you would build it:

```bash
docker build -t webapp-color:lite .
```

By changing the base image to `python:3.6-alpine`, you reduce the size of the final image.
