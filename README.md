# DiZed Docker Compose for working with AWS

## Structure

**The most interesting folders:**

1. **./images** The folder with custom Docker Images.
2. **./local** Folder for local changes. It can be convenient to use it together with the docker-compose.local.yml file.
3. **./mounted** A folder for exchanging files between the PC and the Docker container.
4. **./volumes** The folder with Docker Volumes in Linux structure.
    1. **./volumes/home/projects** Different code for AWS stuff.

## Setup

1. Copy the *./.env.sample* file to the *./.env*. Check it and edit some parameters if needed.
2. Copy the *./volumes/root/bash_history/linux.sample* file to the *./volumes/root/bash_history/linux* for saving command history in the Linux container.
3. **Optional.** Copy the *./docker-compose.local.yml.sample* file to the *./docker-compose.local.yml* and edit it, if you need some changes in the Docker configurations locally.

## Process

**Docker Build**
```code
docker-compose build
```

**Docker Up**
```code
docker-compose up -d
```

Docker Up, if you use some changes for the local environment:

```code
docker-compose -f docker-compose.yml -f docker-compose.local.yml up -d
```

**Docker Stop**
```code
docker-compose stop
```

## Containers

### Linux (Amazon Linux 2023)

- Host: linux

```code
docker-compose exec linux /bin/bash
```
