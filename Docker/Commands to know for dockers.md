# Commands to know for dockers

## Start container:
`docker run -d -p 80:80 docker/getting-started`

`docker run -dp 80:80 [image]`

- -d -> run in background
- -p -> Port -> 
    - First 80: External port. 
    - Second: 80: Internal port.
- image: The las part indicats the image and his version [image/version]

### Expmple hello world
command `docker run hello-world`


# Commands SH and Exec
## Run a command in a container
Running a command by starting the container
`docker run alpine ls -l`

## Open a interactive terminal "SH"
Running a interactive shell
`docker run -it alpine sh`

## Enter in running container "SH"
1. First get the Container_ID -> `docker ps`
2. Execute -> `docker exec -it [Container_ID] sh`


# Info over containers
## Show running container
This command will show the running containers at this moment
`docker ps`

This command shows the last 10 containers including dead ones
`docker ps -a | head`


## Show activiry over a container image
This command will show you the activitys done over the docker file.

`docker image history [docker_ID]`


# Commit container
## Simple commit
Commit a container. Commiting a container make it possible to save changes taht we did on it 

`docker commit [Cointainer_ID]`

## Tag container
Tagging a container make's it easy to name and to version a container
`docker image tag [Container_ID] [name:version]`


# Volumenes
An Volumen is an link between the real world and the dockers world. See it as the portal of TRON. It's the method to get data into the container and store it there.

``



# Creating a container on base on a dockerfile
## Dockerfile
the dockerfile is a set of instructions. This instructions make it possible for docker to create our virtual machines clean and without trash.

#### Example:

We will start with an very easy example. We will create and clean ubuntu image then we will do the next steps:

1. apt-get update -y
2. 


```dockerfile

FROM ubuntu

RUN apt-get update

```

### build our docker file

If we are in the folder where our dockerfile is. Docker will take it an build it. 

`docker build -t MyUbuntu:1.0 .`

to see recent builded docker files.

`docker ls | head`


# Docker-Compose


