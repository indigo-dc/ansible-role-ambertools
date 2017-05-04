[![License](http://img.shields.io/:license-apache-blue.svg?style=flat-square)](http://www.apache.org/licenses/LICENSE-2.0.html)
[![Build Status](https://travis-ci.org/indigo-dc/ansible-role-ambertools.svg?branch=master)](https://travis-ci.org/indigo-dc/ansible-role-ambertools)

Role and Dockerfile for Ambertools
==================================

Roles and Dockerfiles to install the Ambertools v16

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

1. ambertools_url: Ambertools tarball URL
2. amber_home: Ambertools installation directory

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

The example can be run as follows:
```
# export AMBERHOME=/usr/local/amber16
# export PATH=$PATH:$AMBERHOME/bin
# export LD_LIBRARY_PATH=$AMBERHOME/lib
# source $AMBERHOME/amber.sh
# cd $AMBERHOME/AmberTools/benchmarks/nab
# time ./bench_amber gcn4p1
```
License
-------

Apache v2

Author Information
------------------

Mario David: <mariojmdavid@gmail.com>

LIP Lisbon: http://www.lip.pt

Indigo DataCloud: https://www.indigo-datacloud.eu/

Acknowledgments
---------------

Amber and AmberTools are the work of:
D.A. Case, J.T. Berryman, R.M. Betz, D.S. Cerutti, T.E. Cheatham, III, T.A. Darden, R.E. Duke,
T.J. Giese, H. Gohlke, A.W. Goetz, N. Homeyer, S. Izadi, P. Janowski, J. Kaus, A. Kovalenko,
T.S. Lee, S. LeGrand, P. Li, T. Luchko, R. Luo, B. Madej, K.M. Merz, G. Monard, P. Needham,
H. Nguyen, H.T. Nguyen, I. Omelyan, A. Onufriev, D.R. Roe, A. Roitberg, R. Salomon-Ferrer,
C.L. Simmerling, W. Smith, J. Swails, R.C. Walker, J. Wang, R.M. Wolf, X. Wu, D.M. York and P.A. Kollman (2015),
AMBER 2015, University of California, San Francisco.

http://ambermd.org/
