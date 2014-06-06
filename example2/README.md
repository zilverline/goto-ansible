# Multihost example

## Commands

  vim Vagrantfile
  vagrant up --no-provision --no-parallel --provider docker
  export DOCKER_HOST=tcp://localhost:4243
  vagrant status
  docker ps
  ansible-playbook -i hosts setup.yml
  http://192.168.10.10:8800
  http://admin:admin@192.168.10.10:8800/haproxy?stats=true
  ansible-playbook -i hosts update.yml

## Other

export VAGRANT_DEFAULT_PROVIDER=docker

## Docker commands

docker run -i -t ubuntu bash -l
docker ps
