# Commands used to configure MySQL connection at EC2 Instance using MySQL Workbench

## Step 1: 
sudo su

## Step 2: 
cd /etc/mysql/mysql.conf.d

## Step 3: Open file mysqld.cnf
sudo nano mysqld.cnf

## Step 4: Change 2 line bin-address and mysqlx-bind-address
Before: 
bin-address = 127.0.0.1
mysqlx-bind-address = 127.0.0.1
After:
#bin-address = 127.0.0.1
#mysqlx-bind-address = 127.0.0.1
bin-address = 0.0.0.0
mysqlx-bind-address = 0.0.0.0

## Step 5: Restart mysql service
systemctl restart mysql.service

## Step 6: Return mysql
sudo mysql

## Step 7: Create user
CREATE USER 'admin'@'%' IDENTIFIED WITH mysql_native_password BY '1234567890';

## Step 8:
GRANT ALL ON *.* to 'admin'@'%'

## Step 9:
FLUSH PRIVILEGES;

## Step 10: Connect MySQL from MySQL Workbench with user admin and password


