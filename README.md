# dockercmd

Just my cheat sheet for Docker commands. Commands are below with expected output at the time. Some these commands I learned in Derek Morgan's, More Than Certified 

### Print version information and quit
```zsh
$ docker --version
```
### Show the Docker version information
```zsh
$ docker version
  ```

### Display system-wide information
```bash
$ docker info
```

### Display the Docker hierarchy
```zsh
$ sudo tree -L 1 /var/lib/docker/
/var/lib/docker/
├── buildkit
├── containers
├── image
├── network
├── overlay2
├── plugins
├── runtimes
├── swarm
├── tmp
├── trust
└── volumes

11 directories, 0 files
```

### List images
```zsh
$ docker images
```
### Remove all Docker images
```zsh
$ docker rmi -f $(docker images -a -q)
```

### Search and pull Docker images
```zsh
$ docker search <package name>
```
e.g.

```zsh
$ docker search --filter is-official=true node
```

```zsh
$ docker pull node
```

## Docker history commands

### Search Docker image history
```zsh
$ docker history <IMAGE ID>
```

```zsh
$ docker history --format "{{.ID}} {{.CreatedBy}} {{.Size}}" $(docker images -q)
```

### Docker create command
```zsh
$ docker create
```

### Show running all docker containers and size
```zsh
$ docker ps -as
```

### Run a container and rm it after exiting
```zsh
$ docker run -it --rm --name python3 <container name>
```

### Run a named interactive container detached
```zsh
$ docker run --name python3 -itd <container name>

```

### Attach to a running interactive detached container
```zsh
$ docker exec -it python3 <command>
$ docker exec -it python3 python
$ docker exec -it python3 /bin/sh
```

### Attach to a running interactive detached container. When exiting the container will die if not detached.
```zsh
$ docker attach python3
```

