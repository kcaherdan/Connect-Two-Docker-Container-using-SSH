# Connect-Two-Docker-Container-using-SSH
Setting up and establishing a Secure Shell connection between two Ubuntu containers in docker.

![275672018-e3f22697-fd80-41a5-b84c-5d6170c43093](https://github.com/kcaherdan/Connect-Two-Docker-Container-using-SSH/assets/71196354/21b1cc93-4752-47a9-829d-01d1bafd6370)

Run an Ubuntu Server Container----- The initial docker container to run.
1. **To pull Ubuntu Image**

docker pull ubuntu

&nbsp;
**check image is pulled or not**

docker image ls

2. create first Ubuntu container by,

docker run -it --name sshserver-container ubuntu  
**“ -it** means run container in interactive mode ”

3. **To install SSH-Server**

apt-get install openssh-server -y

4. **Install vim editor**

apt-get install vim -y

5. **configure ssh_config file in first container (sshserver-container)**

vim /etc/ssh/sshd_config

In this file go to the Authentication part and uncomment  
“**permitRootLogin prohobit-password** ” line and change to  
“**permitRootLogin yes** ”
**To check SSHservice start**

service --status-all

**if SSH is not start then write**

service ssh start

**then again check SSH status**

service --status-all

**SSH server started**
