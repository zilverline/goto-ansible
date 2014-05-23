# Multihost example

## Commands

* start vm and docker containers
  vagrant up --no-provision --no-parallel --provider docker
* configure mac os x docker client
  export DOCKER_HOST=tcp://localhost:4243
* provision the machines
  ansible-playbook -i hosts zilverline.key setup.yml
* limit
  ansible-playbook -i hosts setup.yml --limit webserver*

* rolling update
  ansible-playbook -i hosts update.yml

## Other

export VAGRANT_DEFAULT_PROVIDER=docker
