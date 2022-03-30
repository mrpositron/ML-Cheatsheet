# Docker Cheatsheet

## Commands

### Starting the container

Docker runs processes in isolated containers. A container is a process which runs on a host. The host may be local or remote. When an operator executes `docker run`, the container process that runs is isolated in that it has its own file system, its own networking, and its own isolated process tree separate from the host.

### Starting Nvidia PyTorch container

```
docker run  --name \                        # here the name of a container can be specified
        --gpus all \                        # here we can specify the number of GPUs
        -it \                               # interactive mode
        --rm \                              # [Optional] delete the container afterwards
        -v local_dir:container_dir \        # mount the data to local directory
        --ipc=host \                        # if multiprocessing is used
        -p YYYY:XXXX \                      # map a port on a container, XXXX, to a port YYYY on the host.
        --uts \                             # set the UTS namespace mode for the container, 
                                            # 'host': use the host's UTS namespace inside the container
        nvcr.io/nvidia/pytorch:xx.xx-py3    # docker image
```

Example:
```
docker run --name fancy_name --gpus all -it --rm --ipc=host -p 60111:8888 -v $(pwd):/workspace/vol1 --uts='host' nvcr.io/nvidia/pytorch:20.10-py3
```

To start the container after stopping run the following command:
```
 docker start -i  fancy_name
``` 

### Listing containers
* `docker ps` = list all containers
* `docker ps -a` = list all active containers
