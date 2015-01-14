[![Build Status](https://travis-ci.org/willshersystems/ansible-apt.svg?branch=master)](https://travis-ci.org/willshersystems/ansible-apt) [![Ansible Galaxy](http://img.shields.io/badge/galaxy-willshersystems.apt-660198.svg?style=flat)](https://galaxy.ansible.com/list#/roles/2579)

APT
===

Configure APT for use with Ansible. It:

* Updates the APT cache if not done for a given period
* Installs python-apt
* Installs apt-transport-https

While python-apt gets installed automatically by Ansible in more recent versions, apt-transport-https does not.

Requirements
------------

* Debian or Ubuntu

Role variables
---------------

* apt_cache_valid_time

Time in seconds between apt cache updates. Defaults to 3600

Example Playbook
----------------
 
```yaml
---
- hosts: all
  vars:
    apt_cache_age:  7200
  roles:
    - role: willshersystems.apt
      when: ansible_pkg_mgr == 'apt'
```

License
-------

LGPLv3


Author
------

Matt Willsher <matt@willsher.systems>

&copy; 2015 Willsher Systems
