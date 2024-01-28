This repository builds a docker image containing `mongodb` and `miniconda` for easier local database installation.
- Docker provides a uniform way to install MongoDB regardless of host operating system
- The mongodb port will be exposed to the host so that the data can be accessed by `MongoDBCompass` at the host machine

## Install Docker
- Download [Docker Desktop](https://www.docker.com/products/docker-desktop/). Make sure `docker` command is available in the command line.
```bash
docker --help
```

## Build Docker Image
- Build a docker image containing `miniconda` and `mongodb`
```bash
docker images -q my_image | docker build -t my_image .
```
- Start a docker image:
```bash
docker run -p 27017:27017 --name my_image my_image
```

- Close docker image:
```bash
docker ps # check all running images
docker commit my_image my_saved_image
docker stop my_image
```

- Refer to `docker_commands.sh` for more frequently used docker commands


## Install MongoDBCompass
After running the docker image, connect to `mongodb://localhost:27017` in the compass.