Zabbix Server
=========

Installs and setup Zabbix-Server 3.0 in Amazon Linux 2017

Installation
------------

erozario.zabbix-server is an Ansible role distributed globally using Ansible Galaxy. In order to install erozario.zabbix-server role you can use the following command.

    $ ansible-galaxy install erozario.zabbix-server


Role Variables
--------------

    - vars:

      zabbix_url: zabbix.example.com
      zabbix_apache_vhost_port: 80
      zabbix_url_aliases: []
      zabbix_version: 3.0
      zabbix_timezone: America/Sao_Paulo
      zabbix_repo: zabbix
      zabbix_vhost: True
      zabbix_web: true
      zabbix_database_creation: True
      zabbix_database_sqlload: True
      alias: zabbix

      # Database
      database_type: mysql
      database_type_long: mysql

      # zabbix-server specific vars
      server_listenport: 10051
      server_sourceip:
      server_logfile: /var/log/zabbix/zabbix_server.log
      server_logfilesize: 10
      server_debuglevel: 3
      server_pidfile: /var/run/zabbix/zabbix_server.pid
      server_dbhost: localhost
      server_dbname: zabbix-server
      server_dbencoding: utf8
      server_dbcollation: utf8_bin
      server_dbuser: zabbix-server
      server_dbpassword: zabbix-server
      server_dbport: 3306
      #server_tmpdir: /tmp
      server_allowroot: 0
      server_user: zabbix
      server_include: /etc/zabbix/zabbix_server.conf.d

Dependencies
------------

    $ ansible-galaxy install geerlingguy.apache

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:


    - hosts: zabbix
      become: yes
      roles:
        - {role: geerlingguy.apache}
        - {role: zabbix-server, zabbix_url: monitoramento, database_type: mysql, database_type_long: mysql}

License
-------

MIT

Author Information
------------------
https://www.linkedin.com/in/eduardo-rozario/
