# ovh-root
.:.Become the root user and select a password.:.

Setting the root password
~$ sudo passwd root
Enter new UNIX password:
Retype new UNIX password:
passwd: password updated 
successfully

Become root
~$ sudo su -
~#

Next, enable root login and password
~$ sudo sed -i 's/#PermitRootLogin prohibit-password/PermitRootLogin yes/g' /etc/ssh/sshd_config
~$ sudo sed -i 's/PasswordAuthentication no/PasswordAuthentication yes/g' /etc/ssh/sshd_config

Restart the SSH service
~$ service sshd restart
