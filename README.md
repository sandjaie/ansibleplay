# task2

This ansible play is written for nginx installation on centos and ubuntu.
### Prerequisites 
#### Install Ansible:
```
sudo apt-add-repository ppa:ansible/ansible
sudo apt-get update
sudo apt-get install ansible
```

### Create Ansible user
Create Ansible user on the host and target
on the host:
```
sudo adduser ansible
sudo apt-get install sshpass
```

on the target:
```
sudo adduser ansible;sudo passwd ansible
sudo usermod -aG wheel ansible
```

### Need to generate ssh keys to login to the remote hosts

On the host logged in as Ansible:
```
ssh-keygen -t rsa
ssh-copy-id ansible@nginx01.domain.local
```
where nginx01.domain.local is the target machine running CentOS 7
