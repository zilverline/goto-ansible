# Basic examples

## Lessions

* vagrant
* host file
* basic ansible command
* modules
* facts (with setup module)
* ansible process (sftp, ssh, python command)
* cp file (idempotent)
* template + jina2 and vars
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

* show vagrant file
  vim Vagrantfile
* start vm
  vagrant up
* ping
  ping 192.168.10.10
* show hosts
  cat hosts
* ansible ping
  ansible -i hosts all -m ping
* show facts about host
  ansible -i hosts all -m setup
* show running processes on host
  ansible -i hosts all -m command -a "ps -fu vagrant"
* show ps-book.yml
  vim ps-book.yml
* show running processes on host with playbook and show output
  ansible-playbook -i hosts ps-book.yml
* copy a file
  ansible-playbook -i hosts copy-book.yml
* copy again no changes
  ansible-playbook -i hosts copy-book.yml
  ansible -i hosts all -m command -a "ls /tmp"
* copy a template
  ansible-playbook -i hosts template-book.yml
* show the template
  ansible -i hosts all -m command -a "cat /tmp/template"
* show simple-role-book.yml
  vim simple-role-book.yml
* my first role
  ansible-playbook -i hosts simple-role-book.yml
* advanced role
  ansible-playbook -i hosts advanced-role-book.yml
* show tags and vars
  ansible-playbook -i hosts advanced-role-book.yml -t advanced -e ""
