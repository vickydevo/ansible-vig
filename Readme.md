## Installing Ansible  documentation

```
 https://docs.ansible.com/ansible/latest/installation_guide/installation_distros.html#installing-ansible-on-ubuntu
```

## Installing Ansible on Ubuntu
```
sudo apt update
sudo apt install software-properties-common
sudo add-apt-repository --yes --update ppa:ansible/ansible
sudo apt install ansible -y
```
## copy private key into other server  [use scp]

```
scp -i "sadik.pem" sadik.pem ubuntu@ec2-174-129-83-202.compute-1.amazonaws.com:/home/ubuntu/keys
```
## Add server into host_inventory /etc/ansible/hosts


```
[devservers]
server1 ansible_host=3.82.157.147
server2 ansible_host=3.93.143.85
server3 ansible_host=100.24.22.162

[webservers]
web1 ansible_host=192.168.1.101 ansible_ssh_private_key_file=/path/to/private_key.pem
web2 ansible_host=192.168.1.102 ansible_ssh_private_key_file=/path/to/private_key.pem
```
## ansible should identify the path of private key
   adding vars for all servers from all groups

```
[all:vars]
ansible_python_interpreter=/usr/bin/python3
ansible_user=ubuntu
ansible_ssh_private_key_file=/home/ubuntu/keys/sadik.pem
```

## Run playbook

```bash
ansible-playbook --inventory inventory/ansible-import-roles-playbook/hosts ansible-import-roles-playbook.yml
```


## How to find apache is installed or not 

```
type -a apache2 
```


## SSH to EC2 instance

```
ssh -i /c/Users/VIgnan/Downloads/key-pair.pem
 ubuntu@ec2-3-74-153-166.eu-central-1.compute.amazonaws.com
```
