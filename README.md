## TAMP Server
* T for Termux App.
* A for Apache Web Server.
* M for MariaDB database.
* P for PHP Language.

### How to install
Step 1: First of all we are update and upgrade our Termux App packages and repositories.
```bash
apt update && apt upgrade -y
```
Step 2: We are install those packages.
```bash
apt install php php-apache apache2 mariadb phpmyadmin -y
```
if you want to install Composer and SMTP library than try this:
```bash
apt install composer msmtp -y
```