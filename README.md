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

The example can be run as follows:
```
# export AMBERHOME=/usr/local/amber14
# export PATH=$PATH:/usr/lib64/openmpi/bin/:$AMBERHOME/bin
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

Mario David: mariojmdavid@gmail.com
LIP and Indigo-DataCloud project

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
