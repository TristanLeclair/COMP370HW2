# COMP 370 Homework 2 steps to setup Apache web server on EC2 instance

## Install web server and start on fresh Ubuntu instance
```
sudo apt update
sudo apt install apache2
sudo systemctl start apache2
cd /etc/apache2/
```
## Update ports to serve on 8008

Open `/etc/apache2/ports.conf`

Add `Listen 8008`

Open `/etc/apache2/sites-enabled/000-default.conf`

Update `<VirtualHost *:80>` to `<VirtualHost *:8008>`

## Create txt file

Create file `/var/www/html/comp370_hw2.txt` and add text

## Restart apache2 server

`sudo systemctl restart apache2`

## Update security rules

Add inbound rule on EC2 instance to allow all TCP HTTP traffic through port 8008

## Verification

You can access the file at `<ip-address-of-EC2-instance>:8008/comp370_hw2.txt`

To verify that the server is serving the correct ports:
- Install netstat `sudo apt install net-tools`
- Run `netstat -tpnl` and find a local address `:::8008`
