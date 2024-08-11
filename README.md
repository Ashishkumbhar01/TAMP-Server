## TAMP Server

TAMP Server for Android Operating System or Mobile 📱 and Laptops  💻 

![TAMP](./TAMP.png)

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

### PHP and Apache Web Server Configuration.
* First of all we are import our `PHP module` from `libexec`.
* So we are changing our Apache `httpd.conf` file.
```bash
vi $PREFIX/etc/apache2/httpd.conf
```
* Go to line number 65
* put this line of code in your `httpd.conf` file.

```bash
65 LoadModule php_module libexec/apache2/libphp.so
```
* Remove # (Uncomment) from line number 66 `mpm_prefork_module`.
* Add # (commented) from line number 67 `mpm_worker_module`.

Full code here:

```conf
63 Example
64 # LoadModule foo_module modules/mod_foo.so
65 LoadModule php_module libexec/apache2/libphp.so
66 LoadModule mpm_prefork_module libexec/apache2/mod_mpm_prefork.so
67 # LoadModule mpm_worker_module libexec/apache2/mod_mpm_worker.so
68
```

### PHP files Configuration.
* Scrolldown in your Apache's `httpd.conf` file.
* Add this line of code in your `httpd.conf` file.

```bash
532
533   <FilesMatch \.php$>
534      SetHandler application/x-httpd-php
535   </FilesMatch>
536
537 Include etc/apache2/extra/php_module.conf
538
```
 
