
# commands to install mysql database for mlflow

### sudo apt install mysql-server
### sudo apt install mysql-client

check if mysql is installed or not
### mysql --version

Log in to MySQL Server
### sudo mysql -u root

## now we create mlflow_user in MySQL using the following command:
### mysql -u mlflow_user (run this outside of database in ec2 machine)
### CREATE USER 'mlflow_user'@'localhost' IDENTIFIED BY 'mlflow'
### GRANT ALL ON db_mlflow.* TO 'mlflow_user'@'localhost';
### FLUSH PRIVILEGES;

## Create and select the database:
### CREATE DATABASE IF NOT EXISTS db_mlflow;
### use db_mlflow;


To know which user have the access to db_mlflow database and its privileges, we can execute the following command:
## SELECT * FROM mysql.db WHERE Db = 'db_mlflow'\G;

Install the MySQLdb module:
### sudo apt-get install python3-mysqldb
Install MySQL client for Python:
### pip install mysqlclient

## list all the tables using the below command

### show tables;

# connect to a mysql container created using docker compose 

use the below highlighted command to get the ip of the mysql container 

### docker inspect -f '{{range.NetworkSettings.Networks}}{{.IPAddress}}{{end}}' container_name_or_id
<img width="689" alt="image" src="https://github.com/sawansolanki/mlflow-setup-complete/assets/64569965/ec06cd13-06b6-411f-ad69-aae96d80a699">





