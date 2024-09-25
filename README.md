rpi = raspberry pi


1. Build rpi
a.	Find another god damn tutorial

2. Setup OS for rpi (Ubuntu)
a.	Put the SD card into a pc
b.	On said pc, download the imager installer from https://www.raspberrypi.com/software/ 
c.	Use the installer to install the imager
d.	Choose “RASPBERRY PI 4” as hardware
e.	Choose “Other general-purpose OS > Ubuntu > Ubuntu Desktop 24.04.1 LTS  (64-bit)” as OS
f.	Choose “SDHC SCSI Disk Device” as storage
g.	Click “NEXT>YES” 
h.	When it’s done downloading, take out the sd card
i.	Put the sd card back into the rpi

3. Install all other things
a.	Write all the following commands{

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

}

open MariaDB with this command{

sudo mariadb –u root

}

in MariaDB write these commands to create a user{

CREATE USER 'username'@'localhost' IDENTIFIED BY 'password';
GRANT ALL PRIVILEGES ON *.* TO 'username'@’localhost’ IDENTIFIED BY 'password';
FLUSH PRIVILEGES;

}