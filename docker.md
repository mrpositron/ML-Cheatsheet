# Docker Cheatsheet

## Commands

### Starting the container

Docker runs processes in isolated containers. A container is a process which runs on a host. The host may be local or remote. When an operator executes `docker run`, the container process that runs is isolated in that it has its own file system, its own networking, and its own isolated process tree separate from the host.

### Starting Nvidia PyTorch container

```
docker run --gpus all \                     # here we can specify the number of GPUs
            -it \                           # interactive mode
            --rm \                          # [Optional] delete the container afterwards
            -v local_dir:container_dir \    # mount the data to local directory
            --ipc=host \                    # if multiprocessing is used
            nvcr.io/nvidia/pytorch:xx.xx-py3
```

Example:
```
docker run --gpus all -it --rm --ipc=host nvcr.io/nvidia/pytorch:20.10-py3
```

### Listing containers
* `docker ps` = list all containers
* `docker ps -a` = list all active containers
