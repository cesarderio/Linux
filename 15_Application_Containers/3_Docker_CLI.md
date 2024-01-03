# Docker CLI: Mastering Container Management

<br>

## Introduction to Docker CLI

The Docker Command Line Interface (CLI) is crucial for interacting with the Docker Engine. This demonstration focuses on familiarizing users with the CLI commands to manage Docker containers efficiently on a Linux host.

<br>

### Verifying Docker Engine Status

1. **Checking Docker Service**:
   - Command: `sudo service docker status`
   - Confirmation: Ensuring the Docker daemon is 'active' and 'running'.

<br>

### Exploring Docker CLI Commands

1. **Basic CLI Command**:
   - Example: `sudo docker`
   - Purpose: Lists available Docker commands for further actions.

2. **Removing Images**:
   - Command: `sudo docker rmi`
   - Usage: Requires at least one argument (container image name) to remove an image.

3. **Getting Command Help**:
   - Command: `sudo docker [command] --help`
   - Function: Provides detailed help and options for specific Docker commands.

<br>

### Important Docker Commands

1. **Checking Docker Version**:
   - Command: `sudo docker version`
   - Provides: Information on the Docker Engine and CLI version, API version, etc.

2. **Listing Docker Images**:
   - Command: `sudo docker images`
   - Displays: Locally stored container images on the Docker host.

3. **Downloading Container Images**:
   - Command: `sudo docker pull [image_name]`
   - Example: `sudo docker pull caddy`
   - Function: Downloads specified container image from a repository (default: Docker Hub).

<br>

### Running Containers

1. **Running a Container**:
   - Command: `sudo docker run -p [port_mapping] [image_name]`
   - Example: `sudo docker run -p 80:80 caddy`
   - Note: Maps local port to port within the container, useful for web server containers like Caddy.

2. **Viewing Running Containers**:
   - Command: `sudo docker ps`
   - Shows: Currently active Docker containers.

3. **Viewing All Containers**:
   - Command: `sudo docker ps -a`
   - Reveals: All containers, including previously run and currently inactive ones.

<br>

### Advanced Docker CLI Usage

1. **Management Commands**:
   - Example: Swarm management for cluster support.
   - Purpose: Handles advanced container orchestration and networking.

2. **Utility Commands**:
   - Examples: `docker build`, `docker cp`, `docker exec`
   - Functions: Building images, copying files between containers and host, executing commands within containers.

<br>

## Conclusion

The Docker CLI is a powerful tool for managing Docker containers and images. Understanding the syntax and capabilities of various commands, such as running, removing, and inspecting containers and images, is essential for effective Docker management. Experimentation in a sandbox environment is recommended for those new to the Docker CLI.
