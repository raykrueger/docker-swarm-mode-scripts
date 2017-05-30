# docker-swarm-mode-scripts

These scripts use docker-machine from the [Docker for Mac][1] distribution to
create a docker swarm-mode cluster and clean it up when you're done.

## prerequisites

You will need Docker for Mac 1.12 or 17.x CE (or better) for this to work.

## create-swarm

Clone this repository and execute `./create-swarm`. This will build 6
virtualbox hosts using docker-machine. Three nodes will be created as
managers and an additional three joined as workers.

## install-visualizer

If you find the Docker Swarm Visualizer tool useful you can install it by
executing `./install-visualizer`. This installs the visualizer to manager-1
where it can talk to the Docker socket, learn what is running in the cluster,
and dispaly it.

The visualizer runs on the manager-1 ip, instructions for browsing are printed
after execution.

## install-registry

Another useful tool is the docker registry, accessible by the cluster and your
local machine. Keys and certs are generated which are then distributed to the
cluster nodes. The registry is isntalled on manager-1 and accessible from your
host machine. This is very useful for building images locally and pushing them
into the cluster registry, and then deploying services from those images.

Instructions for connecting from your local machine are provided at the end of
the script. Essentially this includes adding the ca.crt to your system keystore
and making an /etc/hosts entry.

## destroy-swarm

When you're done playing around execute `./destroy-swarm` to destroy all the
hosts that were created.

[1]: https://docs.docker.com/docker-for-mac/
