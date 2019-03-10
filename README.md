# Run Falcon Ruby app

This Ansible playbooks will run Falcon Ruby app with self-signed TLS/SSL key.

### Ansible setup
First of all, you have to [install Ansible](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html) through package manager or pip and clone this repo:
``` bash
https://github.com/amnkh/falcon.git
```
To run this playbooks, first edit group_vars and enter your details like:
```
domain_fqdn_address: falcon.example.net
ubuntu_server_version: bionic
set_timezone: Asia/Tehran
```
Now create your host file in falhon directory:
``` bash
cd ~/falcon && vim hosts
```
hosts:
```
[falcon]
falcon.example.net

[all:vars]
ansible_ssh_user=root
ansible_ssh_port=22

[falcon:vars]
ansible_ssh_host=192.168.1.10

```
Then change directory to Ansible playbooks root directory and run:
``` bash
ansible-playbook  -i hosts main.yml
```
