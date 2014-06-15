# Rackspace example

export RAX_CREDS_FILE=~/.rackspace_cloud_goto_credentials

ansible-playbook -i inventory/ setup.yml

ansible -i inventory/ goto -u root -m ping

ansible -i inventory/ goto -u root -m setup -a "filter=ansible_default_ipv4.address"

ansible-playbook -i inventory/ ../example2/setup.yml -u root -e html_root=/var/www

ansible-playbook -i inventory/ destroy.yml
