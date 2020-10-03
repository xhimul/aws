## Install Linux, Nginx, MySQL, PHP
## Apache2
- $ `sudo apt update` enter root password
- $ `sudo apt install apache2`
- $ `sudo systemctl status apache2`
- $ `sudo systemctl is-enabled apache2`
- http://YOUR_SERVER_IP


## MySQL
- $ `sudo apt install mysql-server` enter Y to install
- $ `sudo systemctl status mysql`
- $ `sudo systemctl is-enabled mysql`
- $ `sudo mysql_secure_installation` to run automated securing script
- Press N for VALIDATE PASSWORD plugin
- Set root password
- Remove anonymous users? Y
- Disallow root login remotely? N
- Remove test database and access to it? Y
- Reload privilege tables now? Y
- `sudo mysql` to enter MySQL CLI
- `SELECT user,authentication_string,plugin,host FROM mysql.user;` to verify root user's auth method
- `ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'STRONG_PASSWORD_HERE';` to set a root password
- `SELECT user,authentication_string,plugin,host FROM mysql.user;` to verify root user's auth method
- `FLUSH PRIVILEGES;` to apply all changes
- `mysql -u root -p` to access db from now on, enter password STRONG_PASSWORD_HERE



## LAMP
- https://www.tecmint.com/install-lamp-with-phpmyadmin-in-ubuntu-20-04/

## Create/Drop/Show Database
root@TecMint:~$ `sudo mysql -u root -p`\
MariaDB [(none)]> `CREATE DATABASE BookstoreDB;`


## Create User to Access the BookstoreDB Database
MariaDB [BookstoreDB]> `CREATE USER 'bookstoreuser'@'localhost' IDENTIFIED BY 'YourPasswordHere';`\
MariaDB [BookstoreDB]> `GRANT ALL PRIVILEGES ON  BookstoreDB.* to 'bookstoreuser'@'localhost';`\
MariaDB [BookstoreDB]> `FLUSH PRIVILEGES;`




-----------------------------
##### Part 1: Learn MySQL / MariaDB for Beginners
- https://www.tecmint.com/learn-mysql-mariadb-for-beginners/

##### Part 2: Learn How to Use Several Functions of MySQL and MariaDB
- https://www.tecmint.com/learn-mysql-mariadb-advance-functions-sql-queries/


##### MySQL Database Administration Part – 1
##### MySQL Database Administration Part – 2
##### MySQL Performance Tunning and Optimization – Part 3


###### Login with authentication key:
- `sudo ssh -i "bKash_B2C_Key.pem" ubuntu@XX.XX.XX.XX`

##### File send to remote server:
- `sudo scp -i bKash_B2C_Key.pem -r bkash2/ ubuntu@XX.XX.XX.XX:/home/ubuntu/`

##### File move one to another directory
- `sudo mv /home/ubuntu/bkash2/ /var/www/html/ -ifv`

##### File Remove:
- `sudo rm /filename -rfv`


###### Show subdirectory usage memory with summary:
`foodpanda:~ # du /var/spool/asterisk/monitorDONE/ -hc` [-h for human readable, -c for total]
###### Output:
`4.0K    /var/spool/asterisk/monitorDONE/OGG`\
`4.0K    /var/spool/asterisk/monitorDONE/GSM`\
`4.0K    /var/spool/asterisk/monitorDONE/GSW`\
`220G    /var/spool/asterisk/monitorDONE/ORIG`\
`4.0K    /var/spool/asterisk/monitorDONE/GPG`\
`4.0K    /var/spool/asterisk/monitorDONE/FTP2`\
`4.0K    /var/spool/asterisk/monitorDONE/FTP`\
`146G    /var/spool/asterisk/monitorDONE/MP3`\
`366G    /var/spool/asterisk/monitorDONE/`\
`366G    total`

###### Show directory usage memory summary:
`foodpanda:~ # df -h /var/spool/asterisk/monitorDONE/`
###### Output:
`Filesystem      Size  Used Avail Use% Mounted on`\
`/dev/sda3       476G  393G   83G  83% /`


###### Remove all in mentioned directory:
`foodpanda:/var/spool/asterisk/monitorDONE/ORIG # rm -rfv 202007*`


### Show directory usage memory summary
Command: `[root@foodpandaIPPBX ~]# du /var/spool/asterisk/monitor/2020/ -sh` [-s for summary , -h for human readable]\
Output: `194G    /var/spool/asterisk/monitor/2020/`


##### File Download from remote (Windows Subsystem Ubuntu)
- `shimul@TechSolutions:~$ scp root@27.147.XXX.XXX:/cronttest.sh "/mnt/d/vicidial/27.147.XXX.XXX_audio_backup/2020"`



##### Set Time Zone:
sudo timedatectl set-timezone Asia/Dhaka

##### Install & Add Cron:
sudo apt install cron\
sudo systemctl enable cron\
sudo vim /var/spool/cron/crontab/ubuntu\
*/1 * * * * sleep 10; wget -q -O - https://example.com >/dev/null 2>&1\
*/1 * * * * sleep 20; wget -q -O - https://example.com >/dev/null 2>&\
*/1 * * * * sleep 30; wget -q -O - https://example.com >/dev/null 2>&1\
*/1 * * * * sleep 40; wget -q -O - https://example.com >/dev/null 2>&1\
*/1 * * * * sleep 50; wget -q -O - https://example.com >/dev/null 2>&1\


##### See Cron Log:
grep CRON /var/log/syslog\

##### Bash for cron:
#!/usr/bin/env bash\
wget https://https://example.com\
wget https://https://example.com\
saved at /var/www/html/cron.sh\
chmod +x /var/www/html/cron.sh\
