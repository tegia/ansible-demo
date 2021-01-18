# Install Ansible on Control Machine
sudo apt update
sudo apt install ansible
sudo nano /etc/ansible/hosts
[servers]
server1 ansible_host=203.0.113.111
server2 ansible_host=203.0.113.112
server3 ansible_host=203.0.113.113

[all:vars]
ansible_python_interpreter=/usr/bin/python3
# Ansible playbook: Init

An Ansible playbook that installs all common tool on Linux.

## Roles:

- user: Create new user
- zsh: install and config plugin for zsh 
- docker: install docker, docker-compose, ctop

## Role Variables

### user

- username: (string) username of user
- password: (string) encrypted password of user

Note: Generate encrypted password by `mkpasswd`:

```sh
sudo apt-get install -y whois
mkpasswd --method=sha-512
```

### zsh:

- zsh_user: (string) install zsh for this user

### docker:

- docker_users: (list) add this list user to docker group.