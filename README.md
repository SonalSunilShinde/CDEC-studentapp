# MariaDB Setup and Configuration Guide for Windows

This guide explains how to set up MariaDB, create a database, and Create Database User

## 1. Installing MariaDB

Installing MariaDB on Ubntu

```shell
apt update && apt install mariadb-server -y
```

## 2. Securing MariaDB

Open the Command Prompt as Administrator and run the following command to secure your installation:

```shell

mysql_secure_installation
```

Follow the prompts to:
Set a root password.
Remove insecure default users and test databases.
Disable remote root login.

## 3. Setting Up the Database

Open terminal and login to MariaDB:

```bash

mysql -u root -p
```
---

# if you are using RDS database 
install client to connect database to server 
```
sudo apt update
sudo apt install mysql-client
```
```
mysql -h <endpoint> -u <username> -p
```


Enter the root password when prompted.

Create a new database and user:

```sql
CREATE DATABASE student_db;
GRANT ALL PRIVILEGES ON springbackend.* TO 'username'@'localhost' IDENTIFIED BY 'your_password';
```
## in this case if Password Redhat123 and used ec2 instance DB 
```
CREATE DATABASE student_db;
```
```
use student_db;
```
```
GRANT ALL PRIVILEGES ON springbackend.* TO 'root'@'localhost' IDENTIFIED BY 'Redhat123';
```

## if DB-instance were used then use this queary
```sql
CREATE DATABASE student_db;
GRANT ALL PRIVILEGES ON springbackend.* TO 'admin'@'localhost' IDENTIFIED BY 'Redhat123';
```



Replace username and your_password with your desired username and password.

Exit MariaDB:

```sql

EXIT;
```

## 4. You will need Database Credentials to Connect Backend with Database
1. DB_HOST
2. DB_USER
3. DB_PASS
4. DB_PORT
5. DB_NAME

CHANGES DONE BY DEV





# history 
### backend 
```
 1  apt update -y 
    2  git clone https://github.com/mukundDeo9325/CDEC-studentapp.git
    3  ls
    4  apt update && apt install mariadb-server -y
    5  mysql_secure_installation
    6  mysql -u root -p
    7  ls
    8  cd CDEC-studentapp/
    9  ls
   10  cd backend/
   11  ls
   12  cd src/main/resources/
   13  vim application.properties 
   14  cd
   15  cd CDEC-studentapp/
   16  ls
   17  cd backend/
   18  ls
   19  java -version
   20  apt update && apt install openjdk-17-jdk -y
   21  java -version
   22  apt install maven -y
   23  ls
   24  mvn clean package
   25  ls
   26  ls target/
   27  java -jar target/student-registration-backend-0.0.1-SNAPSHOT.jar 
   28  mysql -u root -p 
   29  history

```
### frontend 
```
  1  apt update 
    2  git clone https://github.com/mukundDeo9325/CDEC-studentapp.git
    3  ls
    4  cd CDEC-studentapp/
    5  cd frontend/
    6  ls
    7  ls 
    8  ls -a
    9  vim .env 
   10  apt update && apt install nodejs npm -y
   11  node -v
   12  npm -v
   13  npm install
   14  npm run build
   15  apt install apache2 -y
   16  systemctl start apache2
   17  cp -rf dist/* /var/www/html/
   18  history
```
### MySQL History
```
CREATE DATABASE student_db;
use student_db;
GRANT ALL PRIVILEGES ON springbackend.* TO 'root'@'localhost' IDENTIFIED BY 'Redhat123';
exit ;
```


### To check were data is stored or not check steps in Backend server 
```
show databases;
use student_db;
show tables ;
select * from user ;
```




















