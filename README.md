Setup your rpi <br>
rpi = raspberry pi
 <br>
 <br>


1. Build rpi <br>
a.	Find another god damn tutorial  <br>

2. Setup OS for rpi (Ubuntu)  <br>
a.	Put the SD card into a pc  <br>
b.	On said pc, download the imager installer from https://www.raspberrypi.com/software/  <br>
c.	Use the installer to install the imager  <br>
d.	Choose “RASPBERRY PI 4” as hardware  <br>
e.	Choose “Other general-purpose OS > Ubuntu > Ubuntu Desktop 24.04.1 LTS  (64-bit)” as OS  <br>
f.	Choose “SDHC SCSI Disk Device” as storage  <br>
g.	Click “NEXT>YES”  <br>
h.	When it’s done downloading, take out the sd card  <br>
i.	Put the sd card into the rpi  <br>
 <br>
 <br>

3. Install all other things  <br>
a.	Write all the following commands in the terminal on your rpi 

```
sudo apt update
sudo apt upgrade

sudo apt install ufw
sudo ufw enable
sudo ufw allow ssh

sudo apt install openssh-server
sudo systemctl enable ssh
sudo systemctl start ssh

sudo apt install python3-pip
sudo apt install git
sudo apt install mariadb-server
sudo mysql secure installation
```


<br>
<br>
open MariaDB with this command 

```
sudo mariadb –u root
```


<br>
<br>
in MariaDB write these commands to create a user 

```
CREATE USER 'username'@'localhost' IDENTIFIED BY 'password';
GRANT ALL PRIVILEGES ON *.* TO 'username'@’localhost’ IDENTIFIED BY 'password';
FLUSH PRIVILEGES;
```