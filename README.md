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