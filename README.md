# Rcon

## Introduction
`rcon` is a container runtime similar to `runc` built for the purpose of learning and understanding the key components of containerization tools like Docker and Podman.

## Usage
Create Image
```bash
docker pull ubuntu
CONTAINER_ID=$(docker create ubuntu)
docker export "$CONTAINER_ID" | tar -x -C rootfs
docker rm "$CONTAINER_ID"
```

Build
```bash
go build -o rcon
```

Run
```bash
sudo ./rcon run /bin/sh
```