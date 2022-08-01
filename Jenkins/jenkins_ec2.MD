### jenkins install on ec2 
 [ec2-user ~]$ sudo yum update –y
 ### Java / jenkins install
 ```sh
 [ec2-user ~]$ sudo yum upgrade
 [ec2-user ~]$ sudo amazon-linux-extras install java-openjdk11 -y
 
 #install jenkins
https://pkg.jenkins.io/redhat-stable/
sudo wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/redhat-stable/jenkins.repo
 sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io.key
 yum install fontconfig java-11-openjdk
 yum install jenkins
 
 #Enable the Jenkins service to start at boot
 [ec2-user ~]$ sudo systemctl enable jenkins
 
 #Start Jenkins as a service
 [ec2-user ~]$ sudo systemctl start jenkins
 
 #You can check the status of the Jenkins service using the command
 [ec2-user ~]$ sudo systemctl status jenkins
 #As prompted, enter the password found in /var/lib/jenkins/secrets/initialAdminPassword.
 #Use the following command to display this password:

 [ec2-user ~]$ sudo cat /var/lib/jenkins/secrets/initialAdminPassword
 
 #INSTALL GIT ON AWS
 #Perform a quick update on your instance:
sudo yum update -y
 
#Install git in your EC2 instance
sudo yum install git -y
 
#Check git version
git version
 
 
 ```
