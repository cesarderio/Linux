# Creating a Custom Docker Container Image with a Dockerfile

<br>

## Overview of Dockerfile

- **Dockerfile**: A text file, named `dockerfile`, containing instructions to build a Docker container image.
- **Function**: Used to specify commands, files to be injected, and base image for creating a custom container image.

<br>

## Steps in Building a Custom Image

<br>

### Creating the Dockerfile

1. **Starting the Dockerfile**:
   - Command: `sudo nano dockerfile` to create and edit the Dockerfile.
2. **Defining the Base Image**:
   - `FROM ubuntu:latest` to use the latest Ubuntu image from Docker Hub as a starting point.
3. **Setting Maintainer Info**:
   - `MAINTAINER` keyword to set an email address or maintainer information.

<br>

### Adding Instructions to Dockerfile

1. **Using RUN Command**:
   - For package installation: `RUN apt update && apt install -y tzdata`.
   - For installing Apache: `RUN apt install apache2 -y`.
2. **Copying Files into Image**:
   - `COPY index.html /var/www/html/index.html` to copy a file into a specific location in the container.
3. **Setting CMD Instructions**:
   - `CMD ["apachectl", "-D", "FOREGROUND"]` to ensure Apache runs in the foreground.

<br>

### Saving the Dockerfile

- **Finalizing**: Save and exit the Dockerfile after adding all necessary instructions.

<br>

## Building the Container Image

<br>

### Preparing for Build

1. **Check Existing Images**:
   - Command: `sudo docker images` to view existing images on the host.

<br>

### Building the New Image

1. **Docker Build Command**:
   - `sudo docker build -t myapache2 .` to build the container image named `myapache2` using the Dockerfile in the current directory.

<br>

### Verifying the Build

1. **Checking the New Image**:
   - `sudo docker images` should now show the new image `myapache2`.

<br>

## Running the Custom Container

<br>

### Starting the Container

1. **Docker Run Command**:
   - `sudo docker run -d -p 80:80 myapache2:latest` to run the container in detached mode with port 80 mapping.

<br>

### Troubleshooting Port Issues

1. **Stopping Conflicting Containers**:
   - Use `sudo docker stop [container_name]` if port 80 is already in use.

<br>

### Verifying Container Functionality

1. **Testing with Curl**:
   - `curl http://127.0.0.1:80` should return the contents of the custom web page, confirming the container is running as expected.

<br>

## Conclusion

This demonstration illustrates the process of creating a custom Docker container image using a Dockerfile. It involves setting up a Dockerfile with specific instructions, building the image using Docker CLI commands, and running the container to verify its functionality.
