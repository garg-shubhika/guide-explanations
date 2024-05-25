![image](https://github.com/garg-shubhika/guide-explanations/assets/115157279/ef45b4ae-9c30-4e1b-ac69-0be39fe4d4de)

*Image Source: https://kinsta.com/knowledgebase/what-is-docker/*

- **Docker Client**: The Docker client is a command-line interface (CLI) tool that allows users to interact with the Docker daemon through commands. Users use the Docker client to build, manage, and control Docker containers and images.

- **Docker Daemon**: The Docker daemon (dockerd) is a background service running on the host machine. It listens for Docker API requests from the Docker client and manages Docker objects such as containers, images, networks, and volumes.

- **Containerization**: Docker containers are lightweight, portable, and isolated environments that package applications and their dependencies. Each container runs as an isolated process on the host machine, with its own filesystem, networking, and process space.

- **Images**: Docker images are read-only templates used to create Docker containers. Images contain everything needed to run an application, including the application code, runtime, libraries, and dependencies. Docker images are stored in a registry, such as Docker Hub or a private registry, and can be shared and reused.

- **Registry**: A Docker registry is a repository for storing and distributing Docker images. Docker Hub is the default public registry, which hosts a vast collection of official and community-contributed Docker images. Organizations can also set up private registries to store proprietary or sensitive images.

- **Networking**: Docker provides networking capabilities that allow containers to communicate with each other and with external networks. Docker creates a bridge network by default, enabling containers to communicate with each other on the same host. Users can create custom networks to isolate containers or connect containers to external networks.

- **Storage**: Docker provides various storage options for managing data within containers, including volumes and bind mounts. Volumes are persistent storage volumes that exist independently of the container lifecycle, while bind mounts link container paths to host paths, allowing data to be shared between the container and the host filesystem.
