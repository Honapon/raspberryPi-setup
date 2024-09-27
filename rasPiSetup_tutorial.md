# How to set up your Raspberry Pi

- Download the raspberry Pi image from the official website: https:#www.raspberrypi.com/software/

 - Once you have downloaded the imager, run the setup and open the application and choose your rasperry Pi model, OS(choose other general-purpose OS, and choose ubuntu desktop) and storage device (SD card).
- once the os is downloaded, take your storage device and plug it into your Pi and turn on the Pi. 
- when the Ubuntu setup is configuered and finished, open the command line by pressing **CTRL + ALT + T.** 
    
    - Run theese commands in the terminal. "#" is used infront of comments

``` sh
    #use these to update Ubuntu.
        sudo apt update
        sudo apt upgradre

    #innstall ssh and firewall for remote connection. 
        sudo apt install ufw
        sudo ufw enable
        sudo ufw allow ssh
        sudo apt install openssh-server     

    #enable ssh
        sudo system ctl enable ssh

    # install python, git and Mariadb
        sudo apt install python3-pip
        sudo apt install git
        sudo apt install mariadb-server
        sudo mysql_secure_innstalation
        
    #press enter when asked for a root password,
    and when asked (Y/n) answer: n, n, Y, Y, Y, Y. 
```

- To use ssh you need your Pi's Ip adress.  
```sh
    #finds your ip
        ip a

    #use this command on ur main Pc to ssh to your Pi.
        ssh username@ip

```
## How to setup MariaDB

 to log into mariadb use the command --> *sudo mariadb -u root*. 
 
``` sql
    -- create a user
    CREATE USER 'username'@'localhost' IDENTIFIED BY 'password';

    -- give privileges to user
    GRANT ALL PRIVILEGES ON *.* TO 'username'@'localhost' IDENTIFIED BY 'password';

    -- update rights
    FLUSH PRIVILEGES;

    --replace username and password with your own
```
# Setup for stastic ip

```sh
# To open the ip UI
nmtui

# Move into edit connection and choose either wifi or lan.
# Now go into Ipv4 and change the adress and remember to change from automatic to manual
```
## Transfering files from your pc to your Pi server

```sh
#to transfer files you have to use the scp command
scp c:\Users\Sushi\Downloads\Telefonkatalog_med_database.py liupiu@10.2.3.29:
#this is an example for how it would look
```

## How to download "telefonkatalog_med_database" and use it
```sh
#dowload the file from teams, then run the command:
scp c:\Users\Sushi\Downloads\Telefonkatalog_med_database.py liupiu@10.2.3.29:
```