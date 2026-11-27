jinopl.webserver
================

Ansible role for webserver. ![CI](https://github.com/jinopl/jinopl.webserver/workflows/CI/badge.svg)

Requirements
------------
- Ansible

Role Variables
--------------
- [default ](https://github.com/jinopl/jinopl.webserver/blob/master/defaults/main.yml "default ") Please look into this file , change accordingly. 

### PHP version

| Variable | Default | Meaning |
|---|---|---|
| `php_version` | `""` | `""` uses the OS default PHP. `"X.Y"` (quoted, e.g. `"8.2"`) pins that version. |
| `php_extra_repo` | `auto` | `auto`: add an extra repo only if the OS doesn't provide the pinned version. `always`: always use it. `never`: fail instead. |
| `php_el7_default_version` | `"7.3"` | Used on CentOS/RHEL 7 when `php_version` is empty (the OS only ships PHP 5.4). |
| `php_debian_extensions` / `php_rhel_packages` | see defaults | Extensions/packages to install. |

Extra repository used when the pinned version isn't in the OS repos:

| OS | Repo |
|---|---|
| Ubuntu | `ppa:ondrej/php` |
| Debian | `packages.sury.org/php` |
| CentOS/RHEL 7 | Remi `remi-phpXY` |
| RHEL/Rocky/Alma 8+ | AppStream module stream `php:X.Y` if it exists, otherwise Remi `php:remi-X.Y` |

To switch an already provisioned RHEL host to a different PHP version, remove the
existing PHP packages first; the role fails with a clear message if the installed
version doesn't match the pinned one.

```yaml
vars:
  php_version: "8.2"
```


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
