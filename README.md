Role and Dockerfile for Ambertools
==================================

Roles and Dockerfiles to install the Ambertools:

* https://github.com/haddocking/disvis.git

Introduction
------------

The repository contains ansible-roles that are published in
ansible galaxy: https://galaxy.ansible.com/indigo-dc/ambertools/

The directories docker are linked to
dockerhub with automatic build of image.

Requirements
------------

No aditional requirements

Role Variables
--------------

The variables that can be passed to this role and a brief description
about them are as follows.

1. role variable..

Dependencies
------------

None for now

Install the Playbook
--------------------

To install the role:

```
$ ansible-galaxy install indigo-dc.ambertools
```

Run the playbook
----------------

An example of playbook to deploy ambertools:

```
---
- hosts: localhost
  roles:
    - { role: indigo-dc.ambertools }
```

Or execute:

```
$ ansible-playbook /etc/ansible/roles/indigo-dc.ambertools/tests/ambertools.yml
```


Run the Ambertools application
------------------------------

The example runs disvis on the CPU with 2 threads:

```
$ cd /home
```

License
-------

Apache v2

Author Information
------------------

Mario David: mariojmdavid@gmail.com
LIP and Indigo-DataCloud project

Acknowledgments
---------------

* Ambertools reference here
