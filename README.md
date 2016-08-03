# docker-swarm-mode-scripts

These scripts use docker-machine from the [Docker Toolbox](1) to create a
docker swarm-mode cluster and clean it up when you're done.

## prerequisites

You will need docker-toolbox 1.12 (or better) for this to work.

## create-swarm

Clone this repository and execute `./create-swarm`. This will build 6
virtualbox hosts using docker-machine. Three nodes will be created as
managers and an additional three joined as workers.

## destroy-swarm

When you're done playing around execute `./destroy-swarm` to destroy all the
hosts that were created.

[1]: https://github.com/docker/toolbox/releases
