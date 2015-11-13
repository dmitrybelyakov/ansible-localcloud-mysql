localcloud-mysql
=========

A simple role to install MySQL on an Ubuntu box. Additionally allows you to override what mysql packages to install so you can choose most recent release available from official repositories.

Requirements
------------

This role requires an Ubuntu Box. It was tested on 12 (precise) and 14 (trusty) LTS releases.

Dependencies
------------

This role has no dependencies.


Role Variables
--------------

`mysql_root_password` - required. Set your root password. You can also use this setting to update your password.

`mysql_packages` - optional. A list of packages to install for mysql support. Defaults `mysql-server` and `mysql-client` available from official repositories. But you can override this. For example on Ubuntu trusty you can use 'mysql-server-5.6' and 'mysql-client-5.6' packages instead.


Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

```yml
- hosts: servers
  roles:
     - localcloud-php
  vars:
    mysql_root_password: god
```

License
-------

MIT

