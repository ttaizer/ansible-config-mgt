# Dependences to be installed
====================================
- yum install -y https://dl.fedoraproject.org/pub/epel/epel-release-latest-8.noarch.rpm
- yum install -y dnf-utils http://rpms.remirepo.net/enterprise/remi-release-8.rpm
- yum install python3 python3-pip wget unzip git -y
- python3 -m pip install --upgrade setuptools
- python3 -m pip install --upgrade pip
- python3 -m pip install PyMySQL
- python3 -m pip install mysql-connector-python
- python3 -m pip install psycopg2==2.7.5 --ignore-installed

# Installing  JAVA
====================================
- sudo yum install java-11-openjdk-devel -y

### open the bash profile 
vi .bash_profile 

# paste the below in the bash profile
export JAVA_HOME=$(dirname $(dirname $(readlink $(readlink $(which javac)))))
export PATH=$PATH:$JAVA_HOME/bin
export CLASSPATH=.:$JAVA_HOME/jre/lib:$JAVA_HOME/lib:$JAVA_HOME/lib/tools.jar

# reload the bash profile
source ~/.bash_profile


# Install remi repo, php
=====================================
- yum module reset php -y
- yum module enable php:remi-7.4 -y
- yum install -y php  php-common php-mbstring php-opcache php-intl php-xml php-gd php-curl php-mysqlnd    php-fpm php-json
- systemctl start php-fpm
- systemctl enable php-fpm


# Ansible dependencies to install
=====================================
* For Mysql Database
- ansible-galaxy collection install community.mysql

* For Postgresql Database
- ansible-galaxy collection install community.postgresql

# Install composer
=====================================
- yum install wget 
- curl -sS https://getcomposer.org/installer | php 
- sudo mv composer.phar /usr/bin/composer

### Verify Composer is installed or not
- composer --version


# Install phpunit, phploc
=====================================
- sudo dnf --enablerepo=remi install php-phpunit-phploc
- wget -O phpunit https://phar.phpunit.de/phpunit-7.phar
- chmod +x phpunit
- sudo yum  install php-xdebug

Learn how to install Jenkins [here](https://www.jenkins.io/doc/book/installing/)

Learn how to installk artifactory [here](https://jfrog.com/open-source/)

