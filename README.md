# Setup your rpi <br>
#### (rpi = raspberry pi)
<br>
<br>


### 1. Build your rpi <br>
- Find another god damn tutorial
- A video tutorial or tutorial with pictures might be a good idea  
<br>
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

Setting the root password or using the unix_socket ensures that nobody 
can log into the MariaDB root user without the proper authorisation.

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
- the next output to appear is:
```
 ...skipping.

By default, a MariaDB installation has an anonymous user, allowing anyone 
to log into MariaDB without having to have a user account created for 
them.  This is intended only for testing, and to make the installation 
go a bit smoother.  You should remove them before moving into a 
production encironment.

Remove anonymous users? [Y/n] 
```
- wether you type ***y*** and enter or ***n*** and enter, depends on your current situation
- in this example I type ***n*** and enter
- the next output to appear is:
```
 ...skipping.

Normally, root should only be allowed to connect from 'localhost'.  This 
ensures that someone cannot guess the root password from the network.

Disallow root login remotely [Y/n]
```
- type ***y*** and enter
- the next output to appear is:
```
 ... Success!

By default, MariaDB comes with a datebase named 'test' that anyone can 
access.  This is also intended only for testing, and should be removed 
before moving into a production environment.

Remove the test database and access to it? [Y/n] 
```
- wether you type ***y*** and enter or ***n*** and enter, depends on your current situation
- in this example I type ***n*** and enter
- the next output to appear is:
```
 ... skipping.

Reloading the privilege table will ensure that all changes made so far 
will take effect immediately.

Reload privilege table? [Y/n] 
```
- type ***y*** and enter
- the next (and last) output to appear is:
```
 ... Success!

Cleaning up...

All Done!  If you've completed all of the above steps, your MariaDB 
installation should now be secure.

Thank you for using MariaDB!
```
- you can now move on to the next steps

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