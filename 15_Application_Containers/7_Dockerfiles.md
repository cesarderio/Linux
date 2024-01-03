# Managing Docker Application Containers and Dockerfiles

<br>

## Understanding Dockerfiles

<br>

### Definition

- **Dockerfile**: A text file used to build Docker container images, containing application files and settings.
- **Syntax**: Requires proper syntax and directives for successful image creation.
- **Naming**: File name is one word - 'dockerfile'.

<br>

### Key Points

- **Purpose**: To create new container images based on instructions within the dockerfile.
- **Docker CLI**: The command line interface used for managing all aspects of Docker, including container images.

<br>

## Working with Dockerfiles

<br>

### Key Directives

1. **FROM**: Specifies the base image to start building upon.
2. **COPY**: Copies files from the dockerfile working environment into the container's file system.
3. **ADD**: Similar to COPY, but also allows adding files from URLs.

<br>

### Additional Considerations

- **.dockerignore File**: Used to specify which files or directories to exclude from the Docker container image.
- **Syntax in .dockerignore**:
   - Use `#` for comments.
   - Wildcards (`*` and `?`) for file matching.
   - Square brackets (`[]`) for a range of characters.
   - Exclamation mark (`!`) for logical inversion in file matching patterns.

<br>

## Building and Running a Container Image

<br>

### Docker Build

- **Command**: `docker build -f [path/to/dockerfile]`
- **Tagging**: Use `-t` to tag the new container image (e.g., `mycontainerimage:1.0`).

<br>

### Docker Run

- **Port Mapping**: `-p` to map local ports to container ports.
- **Running a Container**: Use `docker run -p [local_port]:[container_port] [image_name]:[tag]`.

<br>

### Verifying Container Images

- **Viewing Images**: Use `docker images` to see the list of available container images, including the newly created one.
- **Running Containers**: Use `docker ps` to list currently running Docker containers.

<br>

## Conclusion

Dockerfiles are essential for customizing and building Docker container images. Understanding the syntax, directives, and the use of the Docker CLI for building and running containers is crucial for effective Docker management. This allows for the creation of tailored container images suited to specific needs, such as network analysis tools for technicians or development tools for software developers.
