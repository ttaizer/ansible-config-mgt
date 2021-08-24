# Dependences to be installed
====================================
* General
- yum install -y https://dl.fedoraproject.org/pub/epel/epel-release-latest-8.noarch.rpm
- yum install -y dnf-utils http://rpms.remirepo.net/enterprise/remi-release-8.rpm
- yum install python3 
- yum module reset php 
- yum module enable php:remi-7.4 
- yum install python3-pip
- python3 -m pip install --upgrade setuptools
- python3 -m pip install --upgrade pip
- python3 -m pip install PyMySQL
- python3 -m pip install mysql-connector-python
- python3 -m pip install psycopg2==2.7.5 --ignore-installed


# Install remi repo, php and git
=====================================
- yum install -y https://dl.fedoraproject.org/pub/epel/epel-release-latest-8.noarch.rpm
- yum install -y dnf-utils http://rpms.remirepo.net/enterprise/remi-release-8.rpm
- yum install -y  git
- yum module reset php -y
- yum module enable php:remi-7.4 -y
- yum install -y php  php-common php-mbstring php-opcache php-intl php-xml php-gd php-curl php-mysqlnd     php-fpm php-json
- systemctl start php-fpm
- systemctl enable php-fpm

* For Mysql Database
- ansible-galaxy collection install community.mysql

* For Postgresql Database
- ansible-galaxy collection install community.postgresql

* For PHP related process
- yum --enablerepo=remi install php-phpunit-phploc
- yum  install php-xdebug
- yum -y install wget
- wget https://getcomposer.org/installer -O composer-installer.php
- php composer-installer.php --filename=composer --install-dir=/usr/local/bin 



