# Docker

> 2024


___
### Installation   
___ 

- 1 > Download and install Docker at docker.com 
-  2 > Open it <img width="1268" alt="Screenshot 2024-04-26 at 09 46 10" src="https://github.com/louisBerlin/Cheat_Sheet/assets/80892116/dceaf5e3-87eb-4743-8067-bfc997a48f35">

___
### Containers and Images  
___ 

- **Container**: A container is a runtime instance of a Docker image. Within the container, the application runs isolated from the environment.
- **Images**: An image is a self-contained and executable software package that contains everything needed to run an application. It includes the code, runtime environment, system tools, libraries, and settings.

> 💡 Images are read-only and are used to create containers.

___
### Important Docker Commands  
___  

- `docker run --name some-mongo -p 37017:27017 -d mongo:latest`: Runs a container named "some-mongo" based on the "mongo:latest" image in the background mode and maps container port 27017 to host port 37017.

- `docker ps`: Shows a list of running containers.

- `docker ps --all`: Shows a list of all containers, including stopped ones.

- `docker start <container_id>`: Starts a stopped container.

- `docker stop <container_id>`: Stops a running container.

- `docker rm <container_id>`: Deletes a stopped container.

- `docker image rm <image_name>`: Deletes a Docker image.

- `docker images`: Shows a list of available images.

```markdown
- `docker inspect <object_id>`: Displays detailed information about a Docker object (container or image).

- `docker image inspect <image_name>`: Displays detailed information about a specific image.

> 💡 Additional Docker commands and their options can be found in the Docker documentation.

## Resources

- [Docker Documentation](https://docs.docker.com/)
- [Docker Hub](https://hub.docker.com/): A platform for sharing and finding Docker images.
- [Docker Deep Dive](https://dockerbook.com/): A comprehensive book about Docker and containerization.
- [IntelliJ Docker Integration](https://www.jetbrains.com/help/idea/docker.html): Information on integrating Docker with IntelliJ IDEA.
- [Docker explained by Coderized](https://youtu.be/J0NuOlA2xDc?si=4SRbIaJJ_l1uUrJa)
```




