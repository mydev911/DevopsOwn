#### find java installatin dricttory
##### https://youtu.be/c_nF2RnyfDU
```sh
file $(which java)
file /etc/alternateives/java
```
#open .bash_profile
```sh
sudo nano .bash_profile
# java env variable
JAVA_HOME="/usr/lib/jvm/java-11-openjdk-11.0.13.0.8-1.amzn2.0.3.x86_64"
PATH=$JAVA_HOME/bin:$PATH

```
