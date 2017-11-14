# Task2

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

### How to run
pull this repo ```git clone https://github.com/sandjaie/task2.git``` and move to task2 folder and run
```
ansible-playbook -i inventory/domain.local playbooks/install_nginx.yml
```

Directory Structure:
```
├── inventory
│   └── domain.local
├── playbooks
│   ├── files
│   │   └── hosts
│   ├── install_nginx.yml
│   └── roles
│       └── nginx
│           ├── files
│           │   ├── 1.html
│           │   ├── 2.html
│           │   ├── 3.html
│           │   ├── myfirstpage.com.conf
│           │   ├── mysecondpage.com.conf
│           │   ├── mythirdpage.com.conf
│           │   └── nginx.conf
│           └── tasks
│               └── main.yml
└── README.md
```
