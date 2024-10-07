Docker Compose is a tool that simplifies the process of defining and running multi-container Docker applications. It allows you to manage multiple containers with a single configuration file, making it easier to orchestrate the interactions between different services (e.g., databases, web servers, APIs, etc.) in a consistent and scalable manner.

Docker Compose allows you to define and manage multiple services within a single environment. Instead of managing each container individually, you can use a docker-compose.yml file to specify all the containers and their configurations.


## Create docker-compose.yml
``` bash
version: '3'

services:
  web:
    image: nginx  # Nginx image
    ports:
      - "8080:80"  # Map port 8080 on your machine to port 80 in the container

  database:
    image: postgres  # PostgreSQL image
    environment:
      POSTGRES_USER: user  # Database username
      POSTGRES_PASSWORD: pass  # Database password
      POSTGRES_DB: mydb  # Database name
```
