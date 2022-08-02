# Git jenkin ansible pipeline on ec2

### jenkins install
```sh

```
### Ansible install
```sh
#update system packages
sudo yum update
#check if ansible2 repository is enabled
sudo amazon-linux-extras list | grep ansible2
#If not, enable the ansible2 repo
sudo amazon-linux-extras enable ansible2
#install ansible
yum install -y ansible
#To verify the installation, run:
ansible --version
```
#### Now connect Ansible server and Webserver
```sh
#on ansible server
#on ansible inventory file we paste webserver private ip
ec2_user]  vim /etc/ansible/hosts

#insert shift+I
#green.example.com
#blue.example.com
[web]
webserver_private_ip
#exit  esc +:wq

```

### Webserver install
```sh
```
### devloper_server install
