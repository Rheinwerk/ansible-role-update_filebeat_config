Filebeat 6 config update
=========

This role can be used to update a filebeat config, e. g. early in the
startup process before the actual services runs.

[![CI](https://github.com/Rheinwerk/ansible-role-update_filebeat_config/actions/workflows/ci.yml/badge.svg)](https://github.com/Rheinwerk/ansible-role-update_filebeat_config/workflows/ci.yml)

Notice that it will not start the service and expects the program to be
installed already.

Requirements
------------

The target machine must have filebeat in version 6 installed.

Role Variables
--------------
There is one main variable that drives this role: `_filebeat`. It is a map that contains all configuration and settings for this role.
Please see `defaults/main.yml` for details.


Dependencies
------------

None.


Example Playbook
----------------

The general contract of this role is to take the variables map `_filebeat` from `defaults/main.yml` as a template for your configuration and pass that configuration as a parameter to this role.

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      var:
        filebeat:
          ...
      roles:
         - { role: update_filebeat_config, tags: [ 'filebeat' ], _filebeat: "{{ filebeat }}" }

License
-------

Please see LICENSE.

Author Information
------------------

Original author is [Michael Schmitz](https://github.com/eifelmicha) as member of the [Rheinwerk](https://github.com/Rheinwerk) project.
