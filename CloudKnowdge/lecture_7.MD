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
#### install docker on dockerhost
```sh
yum install docker
systemctl start docker
systemctl enable docker
```

###  1.A Enable root  on ansible , jenkins, docker  password
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
##. Jenkins and ansible  password less communication
#### on jenkins server
```sh
ssh-keygen
#enter
#enter
#enter

password we create on ansible follow 1.B
ssh-copy-id -i root@ansible_server_private_ip

#now access webserver from ansible server
ssh root@Web_server_private_ip
#exit
exit


```


## 1.on jenkins dashbord
manage jenkins > magage plugins > avaliable > public over ssh > install.
#### ansible and jenkins userID, password, ip setup
Mange jenkkins > configure system > SSH_Server > 
Name- jenkins  / ansible
HostName- jenkins private ip / ansible private ip 
Useanme- root
> use_password_authentication_use_a_different > password



