# Docker example

This will run a node JS Web app inside a container.

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

# Bonus

Inside folder `redis-example` there's a DockerFile to create a redis image.
