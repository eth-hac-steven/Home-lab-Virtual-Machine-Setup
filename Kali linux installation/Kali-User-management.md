

# Resetting username , hostname , passwd

### 1.1 Hostname
1.1 Set the New Hostname
Use the hostnamectl command to permanently set the new hostname (e.g., cyberops):
```
sudo hostnamectl set-hostname new-hostname
```
### 1.2 Update the Hosts File
You must edit the /etc/hosts file to map the new hostname to the loopback address, otherwise you may encounter "unable to resolve host" errors. Open the file with a text editor like nano:
```
sudo nano /etc/hosts
```
Find the line containing 127.0.1.1 kali and replace kali with your new hostname:
```
127.0.0.1       localhost
127.0.1.1       new-hostname
```
Save and exit the editor. 

### 1.3 Apply Changes
Restart the hostname service to apply the changes immediately without a full reboot:
```
sudo systemctl restart systemd-hostnamed
```
You can verify the change by running ```hostnamectl``` or opening a new terminal session. If you prefer, you can also reboot the VM to ensure all services recognize the new identity


# 2. Username 

### 2.1 Create a tempuser username and password
```
sudo adduser tempuser
```
### 2.2 Add the tempuser to the sudoers group
 ```
sudo usermod -aG sudo tempuser
```
### 2.3 We need  kill any process that  kali may be running and if you are running this on a vm then enter
```
Host key + f4
``` 
(On windows that host key would be right control key)

This opens the tty terminal (big black screen)

login as the tempuser

Then enter 
```
sudo usermod -l new-username -d /home/new-username -m oldusername
```

If this command works then the account has been renamed, skip to step X if not stay with me you should get a 
```
usermod: user kali is currently used by process pid
```
Then enter
```
sudo kill -9 pid
```
This kill the process that kali was running, now run the command
```
sudo usermod -l new-username -d /home/new-username -m oldusername
```
With this the old-username should have changed

Then you want to change the group, enter 
```
sudo groupmod -n new-username oldusername
```
Then enter 
```
su new-username 
```
kill the process that the tempuser is running 

```
sudo killall -u tempuser
```

If you do that the screen will go black and will return you back to kali gui 

login as the new-username

then enter
``` 
userdel tempuser
```
next 
```
rm -r /home/tempuser
```
with this the tempuser is gone and the account has been renamed 


### 3. passwd 
while still login as the new-user enter
```
sudo su
```
Enter the password (which should still be "kali")

Then enter
```
passwd new-user
```
Then enter the new password ,repeat and done. 
