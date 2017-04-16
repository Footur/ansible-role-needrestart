ansible-role-needrestart
================

[![Build Status](https://travis-ci.org/systemli/ansible-role-needrestart.svg)](https://travis-ci.org/systemli/ansible-role-needrestart) [![Ansible Galaxy](http://img.shields.io/badge/ansible--galaxy-needrestart-blue.svg)](https://galaxy.ansible.com/systemli/needrestart/)

Role to install & maintain needrestart 

Role Variables
--------------

Defaults:

    # Admins should be informed via email
    needrestart_disable_email: 0 
    
    ## Restart services (l)ist only, (i)nteractive or (a)utomatically.
    needrestart_action: l
    
    # Email which will be notified
    needrestart_mail_address: $NR_USERNAME
    
    # services which should be ignored
    needrestart_ignorelist: []

Download
--------

Download latest release with `ansible-galaxy`

	ansible-galaxy install systemli.needrestart

Example Playbook
----------------

    - hosts: servers
      roles:
         - { role: systemli.needrestart }



Extended Variables Example
--------------------------

   
    # Admins should be informed via email
    needrestart_disable_email: 0 
    
    ## Restart services (l)ist only, (i)nteractive or (a)utomatically. 
    needrestart_action: a
    
    # Email which will be notified, when a service should be restarted 
    needrestart_mail_address: admin@mydomain.com
    
    # Ignore services below during automatic restart
    needrestart_ignorelist:
      groupname:
         - servicename
      Databases:
         - mysql
         - mongodb
      Mail:
         - exim4
         - dovecot
      Webservers:
        - apache2


License
-------

GPLv3

Author Information
------------------

https://www.systemli.org