# git jenkins ansible dockerhub pipeline

## jenkins setup
```sh
sudo su 
cd
190-] yum install java* -y
Follow lecture 5
```

## Ansible setup
```sh
Follow lecture 5
```
#### install docker on ansible
```sh
yum install docker
```
#### add docker host ip on ansible
```sh
#on ansible
vim /etc/ansible/hosts
#insert shift+I
#green.example.com
#blue.example.com
[docker_hosts]
docker_host_private_ip
#exit  esc +:wq
```
#### ansible and docker keyless communication
#on ansible
```sh
ssh-keygen
ssh-copy-id -i root@docker_private_ip
# change root id on docker Follow 1.A
```

#####  1.A Enable root docker password
```sh
216 ~]# passwd  
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

#now access webserver from ansible server
ssh root@Web_server_private_i
```









