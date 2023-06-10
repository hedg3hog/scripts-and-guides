# Docker Example Files

## Dockerfile

```dockerfile
# syntax=docker/dockerfile:1

FROM node:18-alpine # base image
ENV NODE_ENV=production # environment variable

WORKDIR /app # working directory in the container

# copy files from the host to the container
COPY ["package.json", "package-lock.json*", "./"]

# install dependencies
RUN npm install --production

# copy all files from the host to the container
COPY . .

# expose port 3000
EXPOSE 3000

# command to run when the container starts
CMD ["node", "server.js"]
```

## Docker Compose

in the same directory as the docker-compose.yml file, run:

```bash
docker-compose up -d
# -d runs in detached mode
``` 
to get the containers up and running. And
```bash
docker-compose down
```
to stop them.

[docker-compose.yaml](docker-compose.yaml)

## [Docker Documentation example](https://docs.docker.com/compose/gettingstarted/)

