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

`mysql_packages` - optional. A list of packages to install for mysql support. Defaults 'mysql-server' and 'mysql-client' available from official repositories. But you can override this. For example on Ubuntu trusty you can use 'mysql-server-5.6' and 'mysql-client-5.6' packages instead.

`mysql_bind_address` - optional. Address to bind to. Defaults to local connections from 127.0.0.1.

`mysql_port` - optional. Port to listen for connections on. Defaults to standard 3306.

`mysql_port_open` - bool, optional. Whether to open TCP connections to certain ports on the firewall. Defaults to False. This option together with mysql_users allows you to enable remote connections.

`mysql_users` - optional. A dictionary of users and their connection credentials and privileges. Use this to create users as well as enable remote access. A simple user definition can look like this:

`mysql_binary_log` - optional. Whether binary logging is enabled. Defaults to true, for production. Set to false to disable binary logging locally.

```yml
mysql_users:
  username:
    host: '%'
    password: 'password'
    privileges: '*.*:ALL,GRANT'
```

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

```yml
- hosts: servers
  roles:
     - localcloud-mysql
  vars:
    mysql_root_password: god
```

License
-------

MIT

