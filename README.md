### Project Overview
NGINX Web Server Setup on Ubuntu Linux
this project provides a comprehensive guide for installing, configuring, and managing the NGINX web server on Ubuntu 22.04 LTS.
NGINX is a high-performance, open-source web server renowned for its efficiency and scalability. 
This project focuses on establishing a basic web server to host static websites, configuring virtual servers ,
and implementing log monitoring for maintenance. Designed for beginner-to-intermediate users with basic Linux knowledge,
this documentation offers a practical, streamlined approach to server administration.

## project purpose
This guide provides step-by-step instructions for setting up Apache 2, a popular open-source web server, on Ubuntu Linux.
It includes installation, configuration, basic usage, and troubleshooting tips to ensure a 
functional web server environment. Each section features example commands, file snippets, and explanations to make the process accessible and practical.
## Table of Contents
- Introduction
- Prerequisites
- Installation
- Configuration
- Basic Usage
- Troubleshooting
- Conclusion
## Introduction
Apache 2 (often called Apache HTTP Server) is a robust, widely-used web server software that powers websites across the internet. This guide walks you through setting it up on Ubuntu Linux, 
a beginner-friendly operating system. By the end, you’ll have a working web server capable of hosting simple web pages, with the knowledge to configure and troubleshoot it.

## 2. Prerequisites
Ubuntu Linux installed (this guide uses Ubuntu 22.04 LTS, but steps are similar for other versions).
A terminal with command-line access.
Sudo privileges (administrative rights) to install and configure software.
An internet connection for downloading packages.


## 3. Installation
Step 1: Update the System
Start by updating Ubuntu’s package lists to ensure you install the latest version of Apache.
```
sudo apt update && sudo apt upgrade -y
sudo apt install apache2 -y
sudo systemctl status apache2

```
![nginx status ](https://github.com/rukevweubio/NGINX-Static-Web-Server-on-Ubuntu/blob/main/Screenshot%20(452).png)
## test nginx connection
```nginx -t
```
![nginx status ](https://github.com/rukevweubio/NGINX-Static-Web-Server-on-Ubuntu/blob/main/Screenshot%20(457).png)

## Configuration
- Apache’s configuration files are located in /etc/apache2/
- /etc/apache2/apache2.conf: Main configuration file.
- /etc/apache2/sites-available/: Directory for virtual host files.
- /var/www/html/: Default web root (where web files are stored).

```
 sudo nano /var/www/html/index.html
   sudo nano /etc/nginx/sites-available/site1.com
   server {
    listen 80;
    server_name site1.com www.site1.com;
    root /var/www/site1.com/html;
    index index.html;
    access_log /var/log/nginx/site1-access.log;
    error_log /var/log/nginx/site1-error.log;
}
```
## Troubleshooting
# Install Logwatch
``` sudo apt install logwatch -y
    sudo logwatch --service nginx --range Today --detail Med --format text
    sudo nano /usr/share/logwatch/default.conf/logwatch.conf
```
### conclusion 
This project successfully demonstrates the deployment of NGINX on Ubuntu Linux as of March 13, 2025, tailored for static website hosting. By focusing on installation, virtual server configuration, and log management with Logwatch, it provides a practical foundation for beginner-to-intermediate users. The methodology ensures a functional server.
