# MariaDB setup for remote access

## Install MariaDB

`sudo apt update`
`sudo apt install mariadb-server`
`sudo systemctl start mariadb`

## Change port

In `/etc/mysql/mariadb.conf.d/50-server.cnf`

Add line under `[mysqld]`

`port = 6002`

`sudo systemctl restart mariadb`

Update security settings in EC2 instance to enable traffic to port 6002

## Create DB and add user

`create database comp370_test;`
`CREATE USER 'comp370' IDENTIFIED BY '$ungl@ss3s';`
`GRANT ALL PRIVILEGES ON comp370_test.* TO 'comp370' IDENTIFIED BY '$ungl@ss3s';`


## Verification

Try to connect through DBeaver
