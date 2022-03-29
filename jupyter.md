# Jupyter Notebook

## Running a Jupyter from a remote server

1. Start a Jupyter Notebook on port XXXX on a remote server,

```
remoteuser@remotehost: jupyter notebook --no-browser --port=XXXX
```

2. Forward a port XXXX from a remote server to the port YYYY of the local server,

```
localuser@localhost: ssh -N -f -L localhost:YYYY:localhost:XXXX remoteuser@remotehost -p SS
```
- SS - is a port for `ssh`. Default is 22.

3. Start jupyter notebook locally.

```
localhost:YYYY
```












## References:

- Running a Jupyter notebook from a remote server. Lj Miranda. https://ljvmiranda921.github.io/notebook/2018/01/31/running-a-jupyter-notebook/
