# Docker example

This will run a node JS Web app inside a container.

## To run the example

In the root of the project run:

`$ docker build -t spaceschnoodle/simpleweb . `

spaceschnoodle is my docker hub username.

After building run:

`$ docker run -p 8080:8080 spaceschnoodle/simpleweb`

Now open your browser and go to localhost:8080

![Example of Node web App](/assets/localhost.png "Simple node web app")

# Docker concepts

## Why docker?

Running an app makes big assumptions about the environment and requires precise knowledge of how to start it. Docker solves both these issues. Containers wrap up everything that is needed for a program plus how to start it and run it.

Docker makes it really easy to install and run software without worrying about setup and dependencies.

## What is docker?

Docker is a platform or ecosystem around creating and running containers.

## Example install redis with docker

`$ docker run -it redis`

## Listing running containers

List all running containers:

`$ docker ps`

See all containers that have been created in our machine:

`$ docker ps --all`

## Stop a container

`$ docker stop <container_id>`

## Kill a container

`$ docker kill <container_id>`

## Restarting stopped containers

```
$ docker run busybox echo hi there
$ docker ps --all
$ docker start -a <container_id>
```

## Removing stopped containers

Removes all containers that are stopped:

`$ docker system prune`

After this command we have to redownload the images.

## Retrieving output logs

Just seeing the records, no action.

```
$ docker create busybox echo hi there
$ docker start <container_id>
$ docker logs <container_id>
```

## Multi-commmand containers

First the commmand we want:

`$ docker run redis`

Open a second terminal window to do a redis-cli, we need another command that allows enter text into running container

```
$ docker exec -it <container_id> redis-cli
> set myvalue 5
> get myvalue
> "5"
```

### The purpose of the `it` flag

-t nice indentation
-i communicate with redis-cli input

`it` allows us to have things that we type into our terminal directed into that running process and allow us to get information back into our terminal.

## Getting command prompt in a container

Full terminal access:

```
$ docker exec -it <container_id> sh
# cd /
```

sh is the command processor, now we have full terminal access.  
We use control d or type exit to exit.

# Bonus

Inside folder `redis-example` there's a DockerFile to create a redis image.
