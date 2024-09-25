# Setup your rpi <br>
#### (rpi = raspberry pi)
<br>
<br>


### 1. Build rpi <br>
a.	Find another god damn tutorial  <br>
<br>

### 2. Setup OS for rpi (Ubuntu)  <br>
-	Put the SD card into a pc  <br>
-	On said pc, download the imager installer from https://www.raspberrypi.com/software/  <br>
-	Use the installer to install the imager  <br>
-	Choose “RASPBERRY PI 4” as hardware  <br>
-	Choose “Other general-purpose OS > Ubuntu > Ubuntu Desktop 24.04.1 LTS  (64-bit)” as OS  <br>
-	Choose “SDHC SCSI Disk Device” as storage  <br>
-	Click “NEXT>YES”  <br>
-	When it’s done downloading, take out the sd card  <br>
-	Put the sd card into the rpi  <br>
<br>
<br>

### 3. Install all other things  <br>
-	Write all the following commands in the terminal on your rpi 

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

```

<br>
<br>

- download mariadb with these commands

```
sudo apt install mariadb-server
sudo mysql_secure_installation
```

<br>

- when using the mysql_secure_installation command, you will get asked a few questions
- using the command will produce this output:

```
NOTE: RUNNING ALL PARTS OF THIS SCRIPT IS RECOMMENDED FOR ALL MariaDB
      SERVERS IN PRODUCTION USE!  PLEASE READ EACH STEP CAREFULLY!

In order to log into MariaDB to secure it, we'll need the current
password for the root user.  If you've just installed MariaDB, and
you haven't set the root password yet, the password will be blank,
so you should just press enter here.

Enter current password for root (enter for none):
```
- press enter for none
- the next output to appear is:

```
OK, successfully used password, moving on...

Setting the root password or using the unix_socket ensures that nobody can log into the MariaDB
root user without the proper authorisation.

You already have your root account protected, so you can safely answer 'n'.

Switch to unix_socket authentication [Y/n]
```
- type ***n*** and enter
- the next output to appear is:
```
...skipping.

You already have your root account protected, so you can safely answer 'n'.

Change the root password? [Y/n]
```
- type ***n*** and enter

<br>
<br>

- open MariaDB with this command 

```
sudo mariadb –u root
```


<br>
<br>
-   in MariaDB write these commands to create a user 

```
CREATE USER 'username'@'localhost' IDENTIFIED BY 'password';
GRANT ALL PRIVILEGES ON *.* TO 'username'@’localhost’ IDENTIFIED BY 'password';
FLUSH PRIVILEGES;
```