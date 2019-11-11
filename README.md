freehck.mkdir
=========

Create a bunch of directories

Description
-----------

This role created a bunch of directories. Useful to add as a dependency for other roles.

Role Variables
--------------

`mkdir_directories`: list of directories to create, default is `[]`.

The format of this list is common. It could be a list of strings like `/path/to/dir`, or a list of structures, like this one:

    - path: <path>
      owner: <owner>
      group: <group>
      state: [present|absent]
      recurse: [true|false]

The only mandatory field in this structure is `path`, all the other can be omited. In this case default parameters will be used.

Default values of default parameters:

`mkdir_default_owner`: `root`

`mkdir_default_group`: `root`

`mkdir_default_mode`: `0755`

`mkdir_default_state`: `present`

`mkdir_default_recurse`: `true`

If you need to create a bunch of directories with the same owner, group, etc... feel free to change `mkdir_defaul_*` parameters.

Example
-------

    - role: freehck.mkdir
      mkdir_directories:
        - path: /data/dir1
          owner: root
          group: root
          state: present
          recurse: true
        - path: /data/dir2
        - /data/dir3

Install
-------

This role can be installed from [Ansible Galaxy](https://galaxy.ansible.com/):

`ansible-galaxy install freehck.mkdir`

License
-------

MIT

Author Information
------------------

Dmitrii Kashin, <freehck@freehck.ru>
