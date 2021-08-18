# Dependences to be installed
====================================
* General
- yum install -y https://dl.fedoraproject.org/pub/epel/epel-release-latest-8.noarch.rpm
- yum install -y dnf-utils http://rpms.remirepo.net/enterprise/remi-release-8.rpm
- yum install python3 
- yum module reset php 
- yum module enable php:remi-7.4 
- yum install python3-pip
- python3 -m install --upgrade setuptools
- python3 -m install --upgrade pip


* For Mysql Database
- python3 -m pip install PyMySQL
- ansible-galaxy collection install community.mysql

* For Postgresql Database
- python3 -m pip install python-psycopg2
- ansible-galaxy collection install community.postgresql

* For Posix Firewalld
- ansible-galaxy collection install ansible.posix

* For PHP related process
- yum --enablerepo=remi install php-phpunit-phploc
- yum  install php-xdebug
- yum -y install wget
- wget https://getcomposer.org/installer -O composer-installer.php
- php composer-installer.php --filename=composer --install-dir=/usr/local/bin 




Role Name
=========

A brief description of the role goes here.

Requirements
------------

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
