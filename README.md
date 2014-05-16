# Mac OSX

To use the local Docker client `export DOCKER_HOST=tcp://localhost:4243`

DOCKER_HOST=tcp://localhost:4243 vagrant up --provider docker --provision-with shell --no-parallel

vagrant up --no-provision --no-parallel

ansible-playbook -i hosts -u root --private-key zilverline.key goto.yml
