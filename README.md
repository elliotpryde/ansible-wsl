# Ansible Ubtunu Desktop

Installs development tools for any of my Ubuntu workstations.

## Requirements

### For WSL

- [Docker Desktop](https://www.docker.com/products/docker-desktop)

## Installing

### Install Ansible

```sh
sudo apt update && sudo apt upgrade -y
sudo apt install ansible -y
```

### Get the playbook

```sh
git clone https://github.com:elliotpryde/ansible-ubuntu-desktop.git
ansible-galaxy install -r requirements.yaml
```

### Set your secret variables

Copy `secrets.yaml.tmpl` to `secrets.yaml.tmpl` and fill it with your secrets.

### Run the playbook

```sh
ansible-playbook playbook.yaml --ask-become-pass
```

### Optional

This machine has a Github SSH key now that the playbook has run, so we can update the repository
remote to use SSH authentication.

```sh
git remote rm origin
git remote add origin git@github.com:elliotpryde/ansible-ubuntu-desktop.git
```
