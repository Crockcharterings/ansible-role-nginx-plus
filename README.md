Ansible NGINX Plus Role
=======================

[![Build Status](https://travis-ci.org/nginxinc/ansible-role-nginx-plus.svg?branch=master)](https://travis-ci.org/nginxinc/ansible-role-nginx-plus)

This role installs NGINX Plus on your target host. It supports most CentOS/RHEL/Debian/Ubuntu/SLES distributions.

Requirements
------------

This role was developed using Ansible 2.3.1.0 and as such might not work if a previous version of Ansible is employed.

The following platforms have been tested and are oficially supported:

    CentOS:
      versions:
        - 6
        - 7
    RedHat:
      versions:
        - 6
        - 7
    Debian:
      versions:
      - jessie
      - stretch
    Ubuntu:
      versions:
      - trusty
      - xenial
      - yakkety
    SUSE/SLES:
      versions:
        - 12

Role Variables
--------------

This role has one variable, `certs`, that describes the folder location of the `nginx-repo.crt` and `nginx-repo.key` you received with your NGINX Plus license. By default the role will try to find the folder at `~/certs/`. Your `certs` folder can be located in your local machine if you are deploying to a dynamic inventory or on your target host if you are deploying a simple instance.

Dependencies
------------

None

Example Playbook
----------------

This is a sample playbook file for deploying NGINX Plus from within an online cloud provider.

    ---
    - hosts: localhost
      remote_user: root
      become: true
      roles:
        - role: ansible-nginx-plus
      vars:
        - certs: ~/certs/

This is a sample playbook file for deploying NGINX Plus to a dynamic inventory containing the `nginx` tag.

    ---
    - hosts: tag_nginx
      remote_user: root
      become: true
      roles:
        - role: ansible-nginx-plus
      vars:
        - certs: ~/certs/

License
-------

Simplified BSD License

Author Information
------------------

Alessandro Fael Garcia

**NGINX Inc**
