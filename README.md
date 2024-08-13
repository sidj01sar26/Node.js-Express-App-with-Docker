# Node.js Express App with Docker

## Overview

This project is a basic Node.js application using the Express framework, which is containerized with Docker.<br>
The application listens on port 3000 and serves a simple JSON response at the root endpoint.

## Project Structure

- **Dockerfile**: Defines the Docker image with Node.js, sets the working directory, copies the application code, installs dependencies, and specifies the command to run the app.
- **index.js**: The main application file, which sets up an Express server and handles a basic GET request to return a JSON response.
- **package.json**: Manages the Node.js dependencies, scripts, and project metadata.

## Prerequisites

- Docker installed on your machine.
- Node.js and npm are installed if you want to run the project locally.

## Getting Started

Running the Application with Docker

1. Build the Docker image:

```
docker build -t simple-node-app .
```

2. Run the Docker container:

```
docker run -p 3000:3000 simple-node-app
```

3. Access the application:
   Open your browser and go to [http://localhost:3000](http://localhost:3000) You should see the following JSON response:

```json
{
  "Hey Sid": "Node.js"
}
```

## Docker Commands Overview

- **Pull**: Download an image from a Docker repository.

```
docker pull <image-name>
```

- **Push**: Upload an image to a Docker repository.

```
docker push <image-name>
```

- **Container LS**: List all running containers.

```
docker container ls
```

- **Stop**: Stop a running container.

```
docker stop <container-id>
```

- **Prune**: Remove unused Docker data (stopped containers, networks, etc.).

```
docker system prune
```

- **Port**: Map a container's port to the host machine.

```
docker run -p <host-port>:<container-port> <image-name>
```

## Dockerfile Breakdown

- _`FROM node`_: This line sets the base image to a slim version of Node.js, which is a minimal image suitable for production.
- _`WORKDIR /app`_: Sets the working directory inside the container to /app.
- _`COPY . /app`_: Copies all files from the current directory on the host to the /app directory in the container.
- _`RUN npm install`_: Installs the Node.js dependencies listed in package.json.
- _`EXPOSE 3000`_: Informs Docker that the container will listen on port 3000.
- _`CMD node index.js`_: This command runs the Node.js application when the container starts.

## Documentation & Resources

- [Docker Documentation](https://docs.docker.com/)
- [Docker Hub](https://docs.docker.com/docker-hub/)
- [Node.Js Docs](https://nodejs.org/docs/latest/api/)
- [Express Docs](https://expressjs.com/en/starter/installing.html)