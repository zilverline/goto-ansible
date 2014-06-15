# Basic examples

## Lessons

* vagrant
* host file
* basic ansible command
* modules
* facts (with setup module)
* ansible process (sftp, ssh, python command)
* cp file (idempotent)
* template + jinja2 and vars
* simple role
* advanced role
  * dependencies
  * vars
    - inventory
    - playbook
    - include: other.yml user=bob
    - dependencies in meta/main.yml
    - vars_files
    - command line (--extra-vars "" or -e)
    - register
    - group vars
    - host vars
  * tags (-t one,two --skip-tags three)
  * conditionals
  * handlers
* custom modules..


## Commands

  vim Vagrantfile
  vagrant up
  ping 192.168.10.10

  j 1-ps-book
  vim hosts
  ansible -i hosts all -m ping
  ansible -i hosts all -m setup
  ansible-doc command
  ansible -i hosts all -m command -a "ps -fu vagrant"
  vim playbook.yml
  ansible-playbook -i hosts playbook.yml

  j 2-copy-book
  ansible-playbook -i hosts playbook.yml
  ansible-playbook -i hosts playbook.yml
  ansible -i hosts all -m command -a "ls /tmp"

  j 3-template-book
  ansible-playbook -i hosts playbook.yml
  ansible -i hosts all -m command -a "cat /tmp/template"

  j 4-copy-role-book
  vim playbook.yml
  ansible-playbook -i hosts playbook.yml

  j 5-advanced-role-book
  ansible-playbook -i hosts playbook.yml
  ansible-playbook -i hosts playbook.yml -t advanced -e ""
