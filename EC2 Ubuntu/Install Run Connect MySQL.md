# Commands used to host MySql Server on AWS EC2 Instance

## Step 1: Update the system

sudo apt update

## Step 2: Install MySql

sudo apt install mysql-server

## Step 3: Check the Status of MySql (Active or Inactive)

sudo systemctl status mysql

## Step 4: Login to MySql as a root

sudo mysql

## Step 5: Update the password for the MySql Server

ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'place-your-password-here';

## Step 6:

FLUSH PRIVILEGES;

## Step 7:

sudo su

## Step 8:

cd /etc/mysql/mysql.conf.d

## Step 9: Open file mysqld.cnf

sudo nano mysqld.cnf

## Step 10: Change 2 line bin-address and mysqlx-bind-address

Before:
bin-address = 127.0.0.1
mysqlx-bind-address = 127.0.0.1

After:
#bin-address = 127.0.0.1
#mysqlx-bind-address = 127.0.0.1
bin-address = 0.0.0.0
mysqlx-bind-address = 0.0.0.0

## Step 11: Restart mysql service

sudo systemctl restart mysql.service

## Step 12: Return mysql

mysql -u root -p

## Step 13: Create user

CREATE USER 'admin'@'%' IDENTIFIED WITH mysql_native_password BY '1234567890';

## Step 14:

GRANT ALL ON *.* to 'admin'@'%';

## Step 15:

FLUSH PRIVILEGES;

## Các bước khác

# Bỏ qua bước này

## Step 15: Test the MySql server if it is working by running sample sql queries

CREATE DATABASE mysql_test;

USE mysql_test;

CREATE TABLE table1 (id INT, name VARCHAR(45));

INSERT INTO table1 VALUES(1, 'Virat'), (2, 'Sachin'), (3, 'Dhoni'), (4, 'ABD');

SELECT * FROM table1;

## Step 16: Connect MySQL from MySQL Workbench with user admin and password

## Step 17: Firewall all port for MySQL Workbench

sudo ufw allow from any to any port 3306 proto tcp
