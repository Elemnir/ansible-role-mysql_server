============================
 Ansible Role: mysql_server
============================

Sets up a basic MySQL server using MariaDB. 

----------------
 Role Variables
----------------

Key role variables are documented with their default values below. See ``defaults/main.yml`` for a full list.

::

    mysql_server_datadir: "/var/lib/mysql"

The path to where the MySQL data will be stored.

::

    mysql_server_root_password: ""

The root user password for the server. This must be set.

::

    mysql_server_databases: []

A list of names for databases to define.

::

    mysql_server_users: []

A list of dictionaries, where each item defines a user. Keys are ``username``, ``password``, and ``priv``. ``priv`` should be a string conforming to the MySQL privilege syntax.

------------------
 Example Playbook
------------------

::

    ---
    - hosts: localhost
      vars:
        mysql_server_root_password: "{{ lookup('file', 'mysql_server_password.txt') }}"
      roles:
        - mysql_server
