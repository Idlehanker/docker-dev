[Tutorial site address](https://docs.docker.com/get-started/part2/#define-a-container-with-dockerfile)

```
$ docker build -t friendhello .             #This creates a Docker image, which we’re going to tag using -t so it has a friendly name.
$ docker image ls                           #Where is your built image? It’s in your machine’s local Docker image registry:
$ docker run -p 4000:80 friendhello       #Run the app, mapping your machine’s port 4000 to the container’s published port 80 using -p:
$ docker docker container ls                #list the running container
$ docker run -d -p 4000:80 friendhello    #run the app in the background, in detacted mode
$ docker container ls                       #see the abbreviated container ID
$ docker container stop 1fa4ab2cf395        #to stop the process, using the CONTAINER ID
```
# Part 2
```
docker build -t friendlyhello .  # Create image using this directory's Dockerfile
docker run -p 4000:80 friendlyhello  # Run "friendlyname" mapping port 4000 to 80
docker run -d -p 4000:80 friendlyhello         # Same thing, but in detached mode
docker container ls                                # List all running containers
docker container ls -a             # List all containers, even those not running
docker container stop <hash>           # Gracefully stop the specified container
docker container kill <hash>         # Force shutdown of the specified container
docker container rm <hash>        # Remove specified container from this machine
docker container rm $(docker container ls -a -q)         # Remove all containers
docker image ls -a                             # List all images on this machine
docker image rm <image id>            # Remove specified image from this machine
docker image rm $(docker image ls -a -q)   # Remove all images from this machine
docker login             # Log in this CLI session using your Docker credentials
docker tag <image> username/repository:tag  # Tag <image> for upload to registry
docker push username/repository:tag            # Upload tagged image to registry
docker run username/repository:tag                   # Run image from a registry
```

## key items
```
docker build -t friendlyhello .  # Create image using this directory's Dockerfile
docker run -p 4000:80 friendlyhello  # Run "friendlyname" mapping port 4000 to 80
```

# Part 3 镜像
## 加速
Docker for mac 应用图标 -> Perferences... -> Daemon -> Registry mirrors。在列表中填写加速器地址 https://registry.docker-cn.com

## fetch image
docker pull [选项] [Docker Registry 地址[:端口号]/]仓库名[:标签]
```
$ docker pull ubuntu:16.04
```

