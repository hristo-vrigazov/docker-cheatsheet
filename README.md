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

* Copy current folder into docker container's home folder

```bash
docker cp . 61e6ed03aa66:/home/scientist/.
```

* Run a container connected to your display with given name 

```bash
xhost local:root
docker run -it --name opencv --env="DISPLAY" --env="QT_X11_NO_MITSHM=1" --volume="/tmp/.X11-unix:/tmp/.X11-unix:rw"  tsutomu7/python-opencv
```

* Find the id of a container by name

```bash
sudo docker ps -aqf "name=opencv"
```

* List all images
```bash
docker images
```

* Remove all docker images

```bash
docker rmi -f $(docker images -a -q)
```

* Remove a docker image

```bash
docker rmi ubuntu
```

* Build a docker image by a Dockerfile

```bash
docker build -t example .
```

* Run an image

```bash
docker run example
```

* Tag an existing local image

```bash
docker tag e379ad0b10e0 hvrigazov/example:latest
```

* Steps needed to create a docker image and push it to docker hub

1. Go to docker hub site and create the repository, say 'hvrigazov/example'
2. Create a Dockerfile locally and build it
3. See the id of the image:
```bash
docker images
```
4. Tag it:
```bash
docker tag e379ad0b10e0 hvrigazov/example:latest
```

5. Login:
```bash
docker login
```

6. Push
```bash
docker push hvrigazov/example
```
