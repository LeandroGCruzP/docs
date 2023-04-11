# Docker

<details>
<summary><b>Table of Contents</b></summary>

- [Docker images](#docker-images)
    - [Show images](#show-images)
    - [Downloading new images](#downloading-new-images)
    - [Remove image](#remove-images)
- [Docker network](#docker-network)
    - [Show network](#show-networks)
    - [Create network](#create-network)
    - [Remove network](#remove-network)
- [Docker container](#docker-containers)
    - [Show containers](#show-containers)
    - [Create container from image](#create-container-from-image)
    - [Execute container](#execute-container)
    - [Stop container](#stop-container)
    - [Remove container](#remove-container)
    - [Logs container](#logs-container)
    - [Run container](#run-container)
- [Dockerfile](#dockerfile)
    - [Dockerfile](#dockerfile)
    - [DockerfileIgnore](#dockerfileignore)
</details>

#
## Docker images

### Show images
Return all images downloaded
```bash
docker images
```

### Downloading new images
- [List of docker official images](https://hub.docker.com/search?image_filter=official&type=image&q=)

Downloading latest version of image
```bash
docker pull [name-image]
```

Downloading specific version of image
```bash
docker pull [name-image]:[version-image]
```

### Remove image
Remove latest version
```bash
docker image rm [name-image]
```

Remove specific version
```bash
docker image rm [name-image]:[version-image]
```

#
## Docker network

### Show networks
```bash
docker network ls
```

### Create network
```bash
docker network create [name-network]
```

### Remove network
```bash
docker network rm [name-network]
```

#
## Docker containers

### Show containers
Option   | Description
-------- | ---------
```-a``` | all

Show containers running
```bash
docker ps
```

Show all containers
```bash
docker ps -a
```

### Create container from image
> This command return the ***container id***

Option   | Description
-------- | ---------
```-p``` | publish
```-e``` | environment

Create container with random name
```bash
docker create [name-image]
```

Create container with custom name
```bash
docker create --name [name-container] [name-image]
```

Create container with custom name and random port mapping
```bash
docker create -p[container-port] --name [name-image] [name-image]
```

Create container with custom name and custom port mapping
```bash
docker create -p[local-host-port]:[container-port] --name [name-image] [name-image]
```

Create container with custom name, custom port mapping and environment variables to connect mongo db
```bash
docker create -p[local-host-port]:[container-port] --name [name-image] -e MONGO_INITDB_ROOT_USERNAME=[username_mongo] -e MONGO_INITDB_ROOT_PASSWORD=[password_mongo] [name-image]
```

Create container with custom port mapping, custom name, network and environment variables to connect mongo db
```bash
docker create -p[local-host-port]:[container-port] --name [name-image] --network [name-network] -e MONGO_INITDB_ROOT_USERNAME=[username_mongo] -e MONGO_INITDB_ROOT_PASSWORD=[password_mongo] [name-image]
```

### Execute container
Execute container by id
```bash
docker start [container-id]
```
Execute container by name
```bash
docker start [container-name]
```

### Stop container
Stop container by id
```bash
docker stop [container-id]
```
Stop container by name
```bash
docker stop [container-name]
```

### Remove container
Remove container by id
```bash
docker rm [container-id]
```
Remove container by name
```bash
docker rm [container-name]
```

### Logs container
Docker logs by id
```bash
docker logs [container-id]
```
Docker logs by name
```bash
docker logs [container-name]
```
Docker logs by name with follow ()
```bash
docker logs --follow [container-name]
```

### Run container
> This command return the ***container id***

Option   | Description
-------- | ---------
```-d``` | detached
```-p``` | publish

Find or download [name-image], create container with random name and without port mapping. Finally execute container
```bash
docker run -d [name-image]
```

Find or download [name-image], create container with custom name and with custom port mapping. Finally execute container
```bash
docker run -p[local-host-port]:[container-port] --name [name-image] -d [name-image]
```

#
## Dockerfile

### Dockerfile
Create in your project a file named ```Dockerfile```

Example to NextJS
```Dockerfile
# Install dependencies only when needed
FROM node:alpine AS deps
RUN apk add --no-cache libc6-compat
WORKDIR /app
COPY package.json yarn.lock ./
RUN yarn install --frozen-lockfile

# Rebuild the source code only when needed
FROM node:alpine AS builder
WORKDIR /app
COPY . .
COPY --from=deps /app/node_modules ./node_modules
RUN yarn build

# Production image, copy all the files and run next
FROM node:alpine AS runner
WORKDIR /app

ENV NODE_ENV production

# You only need to copy next.config.js if you are NOT using the default configuration
# COPY --from=builder /app/next.config.js ./
COPY --from=builder /app/public ./public
COPY --from=builder /app/.next ./.next
COPY --from=builder /app/node_modules ./node_modules
COPY --from=builder /app/package.json ./package.json

RUN addgroup -g 1001 -S nodejs
RUN adduser -S nextjs -u 1001
RUN chown -R nextjs:nodejs /app/.next
USER nextjs

EXPOSE 3000

CMD ["yarn", "start"]
```

### DockerfileIgnore
Create in your project a file named ```.dockerfileignore```

Example to NextJS
```
Dockerfile
.dockerfileignore
node_modules
npm-debug.log
README.md
.next
```
