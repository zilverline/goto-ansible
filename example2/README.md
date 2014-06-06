# Multihost example

## Commands

* start vm and docker containers
  vagrant up --no-provision --no-parallel --provider docker
* configure mac os x docker client
  export DOCKER_HOST=tcp://localhost:4243
* provision the machines
  ansible-playbook -i hosts setup.yml
* view its up
  http://192.168.10.10:8800
* view haproxy stats
  http://admin:admin@192.168.10.10:8800/haproxy?stats=true
* rolling update
  ansible-playbook -i hosts update.yml

## Other

export VAGRANT_DEFAULT_PROVIDER=docker

## Docker commands

docker run -i -t ubuntu bash -l
docker ps
