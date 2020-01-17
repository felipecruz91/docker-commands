# containers-lifecycle

## Run

Run the docker image mentioned in the command. This command will create a docker container in which Alpine will run.

```
$ docker run -it -d alpine
```

## What's running?

`ps` lists all the docker containers are running with container details.

```
$ docker ps

CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS              PORTS               NAMES
ba0948b5454f        alpine              "/bin/sh"           15 hours ago        Up 2 seconds                            angry_dubinsky
```

or have a window that refreshes every 2 seconds with `watch`:

```
$ watch docker ps

Every 2.0s: docker ps         DESKTOP-7F4JN2O: Sun Jan 12 09:29:57 2020

CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS              PORTS               NAMES
ba0948b5454f        alpine              "/bin/sh"           15 hours ago        Up 7 minutes                            angry_dubinsky
```

## Restart

Restart the docker container with container id mentioned in the command.

```
$ docker restart ba0948b5454f
```

## Stop

Stop a container with container id mentioned in the command.

```
$ docker stop ba0948b5454f
```

Stop all the running containers:

```
$ docker stop $(docker ps -aq)
```

## List all the containers

List all the docker containers running/exited/stopped with container details.

```
$ docker ps -a

CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS              PORTS               NAMES
ba0948b5454f       alpine              "/bin/sh"           15 hours ago        Up 3 minutes                            angry_dubinsky
```

## Start

This command in docker starts the docker container with container id mentioned in the command.

```
$ docker start ba0948b5454f
```

## Commit
Save a new docker image with container id mentioned in the command on the local system. 

```
$ docker commit ba0948b5454f my-alpine
```

## Kill

Stop the docker container immediately. Docker stop command stops the container gracefully, that’s the difference between a kill and stop commands.

```
$ docker kill ba0948b5454f
```

## Remove

Remove the docker container with container id mentioned in the command.

```
$ docker rm ba0948b5454f
```

Remove all containers

```
$ docker rm $(docker ps -aq)
```
