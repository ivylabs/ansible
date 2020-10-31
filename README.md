# ansible

## Installation

sudo apt update
sudo apt install software-properties-common
sudo apt-add-repository --yes --update ppa:ansible/ansible
sudo apt install ansible

## Without ansible.cfg

ansible all --key-file ~/.ssh/ansible -i inventory -m ping --user root

## Using ansible.cfg

ansible all -m ping --user root

ansible all --list-hosts --user root

ansible all -m gather_facts --user root

ansible all -m gather_facts --user root --limit 134.209.186.106

### sudo apt update

ansible all -m apt -a update_cache=true --user root

ansible all -m apt -a update_cache=true --user root --become --ask-become-pass

### sudo apt install unzip

ansible all -m apt -a name=unzip --user root --become --ask-become-pass

### Run a playbook

ansible-playbook --ask-become-pass install_apache.yml -u root
