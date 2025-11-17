# LAMP Stack & WordPress Installation Guide

A Professional and Comprehensive Deployment Manual

This guide provides a structured, production-ready approach to
installing and configuring a **LAMP (Linux, Apache, MySQL, PHP)** stack
and deploying **WordPress** on a Linux server. It includes theoretical
explanations, best practices, and command references suitable for
learning, interviews, and real-world server setups.

------------------------------------------------------------------------

## 1. Update System Packages & Install Core Components

Keeping your package index updated ensures you install the latest, most
secure versions of required software.

### **Update Package Repository**

``` bash
sudo apt-get update
```

Updates the local package database so the system is aware of the latest
available versions.

### **Install Apache Web Server**

``` bash
sudo apt install apache2
```

Apache is a widely used, stable, and powerful HTTP server that will host
your WordPress site.

### **Install PHP and Required Modules**

``` bash
sudo apt install php libapache2-mod-php php-mysql
```

-   **PHP** -- server-side scripting language\
-   **libapache2-mod-php** -- integrates PHP with Apache\
-   **php-mysql** -- enables PHP--MySQL database communication

### **Install MySQL Server**

``` bash
sudo apt install mysql-server
```

MySQL is the relational database engine used by WordPress to store
posts, settings, and user information.

------------------------------------------------------------------------

## 2. Basic Directory Navigation Commands

Understanding Linux navigation is essential during deployment.

### **List Directory Files**

``` bash
ls
```

### **List Files with Details**

``` bash
ls -l
```

### **Clear the Terminal Screen**

``` bash
clear
```

------------------------------------------------------------------------

## 3. Initial MySQL Configuration

Login to MySQL as the root user to create and manage databases.

``` bash
sudo mysql -u root
```

This command opens the MySQL shell with administrative permissions.

------------------------------------------------------------------------

## 4. Download and Extract WordPress

### **Navigate to Temporary Directory**

``` bash
cd /tmp
```

`/tmp` is ideal for storing temporary installation files.

### **Download Latest WordPress Package**

``` bash
wget https://wordpress.org/latest.tar.gz
```

### **Extract the WordPress Archive**

``` bash
tar -xvf latest.tar.gz
```

------------------------------------------------------------------------

## 5. Deploy WordPress to Apache Web Root

Move extracted WordPress files to the directory served by Apache.

``` bash
sudo mv wordpress/ /var/www/html/
```

------------------------------------------------------------------------

## 6. Navigate to the WordPress Directory

``` bash
cd /var/www/html/
cd wordpress/
```

This is where configuration files such as `wp-config.php` reside.

------------------------------------------------------------------------

## 7. Configure WordPress Settings

Modify the configuration file to set database credentials and security
keys.

### Using Nano

``` bash
nano wp-config.php
```

### Using Vim

``` bash
vim wp-config.php
```

------------------------------------------------------------------------

## 8. Edit Apache Virtual Host Configuration

### Navigate to Apache configuration directory:

``` bash
cd /etc/apache2/sites-available/
```

### Open the default Virtual Host file:

``` bash
sudo vim 000-default.conf
```

This file defines server document roots, log locations, and domain
settings.

------------------------------------------------------------------------

## 9. Apply Changes by Restarting Apache

``` bash
sudo systemctl restart apache2
```

This reloads Apache with updated configurations.

------------------------------------------------------------------------

## 10. Verify Local Hostname Resolution

``` bash
cat /etc/hosts
```

This file maps domain names to local IPs and is useful when setting up
WordPress with custom hostnames.

------------------------------------------------------------------------

## ✔ Deployment Complete

You now have a fully configured **LAMP stack** with **WordPress**
deployed on your server.\
This setup is suitable for: - Development environments\
- Production hosting\
- Learning Linux & DevOps workflows\
- Practicing Apache, MySQL, and PHP management

------------------------------------------------------------------------
