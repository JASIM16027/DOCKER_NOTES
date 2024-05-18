# DOCKER_NOTE
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

### Process State
- A process is an instance of a running program.
- States include running, waiting, or terminated.

### Process ID (PID)
- Unique identifier assigned by the OS to each process.

### Attributes of a Process
- Attributes include total read/write operations, priority level, and other characteristics.

### Context Switching
- The process of saving and restoring the state of a process, allowing the CPU to switch between processes.

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
