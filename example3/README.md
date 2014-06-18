# Rackspace example

export RAX_CREDS_FILE=~/.rackspace_cloud_goto_credentials

ansible-playbook -i inventory/ create.yml

ansible -i inventory/ all -u root -m ping

ansible-playbook -i inventory/ ../example2/setup.yml -u root -e html_root=/var/www --limit webservers

ansible-playbook -i inventory/ destroy.yml
