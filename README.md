# Quick commands for docker

* Run bash inside a container

```bash
docker run -it tsutomu7/python-opencv
```

* Remove all docker containers

```bash
docker rm $(docker ps -a -q)
```

* Stop all docker containers

```bash
docker stop $(docker ps -a -q)
```

* Connect docker container to your display

```bash
docker run -it --env="DISPLAY" --env="QT_X11_NO_MITSHM=1" --volume="/tmp/.X11-unix:/tmp/.X11-unix:rw" tsutomu7/python-opencv
```

* Connect docker container port to your port

```bash
docker run -it -p 1880:1880 --name mynodered nodered/node-red-docker
```