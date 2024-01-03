# Installing Docker Engine on Linux

<br>

## Introduction to Docker Engine Installation

This demonstration covers the installation of the Docker Engine on Ubuntu Linux, essential for running Docker containers. Docker Engine can run on various platforms, including physical servers or virtual machines.

<br>

### Installation Process

1. **Starting Installation**:
   - Command: `sudo apt install docker.io`
   - Disk Space Requirement: Approximately 293 MB.
   - User Confirmation: Typing 'y' for yes to start the installation.

<br>

### Verifying the Installation

1. **Checking Docker CLI**:
   - Command: `sudo docker`
   - Purpose: To confirm that the Docker Command Line Interface (CLI) is installed.

2. **Checking Docker Service Status**:
   - Command: `sudo service docker status`
   - Indicators: 'Active' and 'Running' status confirm the Docker daemon is operational.

<br>

### Working with Docker Images

1. **Listing Docker Images**:
   - Command: `sudo docker images`
   - Function: To display available local container images (initially none).

2. **Docker Hub Access**:
   - Usage: For searching and accessing publicly available container images.

3. **Downloading a Container Image**:
   - Example: `sudo docker pull alpine`
   - Function: Downloads the specified container image from Docker Hub.

<br>

### Running a Docker Container

1. **Starting a Container**:
   - Command: `sudo docker run -it alpine`
   - Mode: Interactive mode with a terminal inside the container.
   - Observation: Quick load time due to the use of the underlying OS on the Docker host.

2. **File System Access**:
   - Action: Typing 'ls' within the container shows its own file system.

3. **Exiting the Container**:
   - Method: Typing 'exit' returns to the host's Command Prompt.

<br>

### Container Management

1. **Viewing Running Containers**:
   - Command: `sudo docker ps`
   - Displays: Currently running containers (none after exiting Alpine container).

2. **Viewing All Containers**:
   - Command: `sudo docker ps -a`
   - Displays: All containers, including those not currently running.

<br>

## Conclusion

This demonstration provided a walkthrough for installing the Docker Engine on Linux, verifying its operation, and running a container. Key steps included installing Docker, verifying the CLI, downloading a container image from Docker Hub, and running a container in interactive mode.
