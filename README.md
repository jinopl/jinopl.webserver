jinopl.webserver
================

Ansible role for webserver. ![CI](https://github.com/jinopl/jinopl.webserver/workflows/CI/badge.svg)

Requirements
------------
- Ansible

Role Variables
--------------
- [default ](https://github.com/jinopl/jinopl.webserver/blob/master/defaults/main.yml "default ") Please look into this file , change accordingly. 


Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

```yaml
---
- hosts: ec2
  become: yes
  roles:
    - jinopl.webserver
  vars:
    domain_name: hulk.com
    userGroupName: marvel
```    
License
-------

BSD

Author Information
------------------
[Jino pl](https://github.com/jinopl "Jino pl")
