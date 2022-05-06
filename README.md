# Dockerize React App

This repo shows how to dockerize react application, using a hello world sample created with [create-react-app](https://create-react-app.dev/).

## Prerequisites

Follow the [instructions](https://docs.docker.com/get-docker) to setup docker locally

## Build docker image locally

Open terminal and go to root of this repository, run following command

```bash
cd react-app
docker build -t blrchen/react-app .
```

Note: you should replace **blrchen/react-app** with the image name you want to use. <user_name>/<image_name> is not a mandatory format for specifying the name of the docker image

## Test docker image locally

Run **docker images** command to see newly created image

```bash
docker images
```

Run **docker run** to test docker image locally

```bash
docker run -it --rm -p 3000:80 blrchen/react-app
```

Open web browser and navigate to <https://localhost:3000>，verify react app is running correctly inside container.

## Upload to Azure Container Registry

Run **docker push** command to see newly created image

```bash
docker tag blrchen/react-app blrchen.azurecr.io/blrchen/react-app
docker push blrchen.azurecr.io/blair/react-app
```

## Files required for building docker images

|File|Description|
|-|-|
|[Dockerfile](./react-app/Dockerfile)|[doc](https://docs.docker.com/engine/reference/builder/) |
|[.dockerignore](./react-app/.dockerignore)|[doc](https://docs.docker.com/engine/reference/builder/#dockerignore-file)|
