# Git jenkin ansible pipeline on ec2

### 1. jenkins install
```sh

```
### 1. Ansible install
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
##### 1. create ansible password
```sh
#on ansible server
passwd root
#then ssh key configration fifle

vim /etc/ssh/sshd_config
#shift+I
#LoginGraceTime 2m
#PermitRootLogin yes
PermitRootLogin yes
#To disable tunneled clear text passwords, change to no here!
#PasswordAuthentication no
PasswordAuthentication yes
Exit Esc+:wq
#resart 
systemctl restart sshd


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

###  1. Webserver install
##### https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_Tutorials.WebServerDB.CreateWebServer.html
```sh
sudo su
yum update
#Install the Apache web server.
sudo yum install -y httpd
#Start the web server
sudo systemctl start httpd
#enable the web_server
sudo systemctl enable httpd
#root login in webserver enable
passwd root
#then ssh key configration fifle
vim /etc/ssh/sshd_config

#shift+I
#LoginGraceTime 2m
#PermitRootLogin yes
PermitRootLogin yes
#To disable tunneled clear text passwords, change to no here!
#PasswordAuthentication no
PasswordAuthentication yes
Exit Esc+:wq
#resart 
systemctl restart sshd

cd /var/www/html/




```
### 2. ansible and webserver password less communication
####on ansible server
```sh
#generate key
ssh-keygen
#enter
#enter
#enter
ssh-copy-id -i root@Web_server_private_ip
#password we create on webserver

#now access webserver from ansible server
ssh root@Web_server_private_ip
#exit
exit
```
### 2. Jenkins and ansible  password less communication
#### on jenkins server
```sh
ssh-keygen
#enter
#enter
#enter
ssh-copy-id -i root@ansible_server_private_ip
#password we create on ansible

#now access webserver from ansible server
ssh root@Web_server_private_ip
#exit
exit


``
### 1. devloper_server install
