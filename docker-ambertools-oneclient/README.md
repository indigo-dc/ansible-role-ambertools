[![License](http://img.shields.io/:license-apache-blue.svg?style=flat-square)](http://www.apache.org/licenses/LICENSE-2.0.html)

# Ambertools

## Introduction
The docker image is Ubuntu 14.04 LTS with AmberTools v16 compiled with
openmpi and with no mpi. The image is prepared to run as an application.

It is built from the ansible-role-ambertools

It depends/installs as well the oneclient in order to use oneprovider

Indigo-DataCloud has produced a tarball of AmberTools15 without the test directories
in order to decrease the size of the image, it is otherwise the same as the official
release: http://www.lip.pt/~david/AmberTools16_indigo-bin.tgz

## Build the docker image

```
docker build -t ambertools-oneclient .
```

Or you can pull from the dockerhub

```
docker pull indigodatacloudapps/ambertools-oneclient
```

## Run the benchmark

The example below will run the sander benchmark.

```
$ docker run indigodatacloudapps/ambertools-oneclient \
/bin/bash -c 'source $AMBERHOME/amber.sh;cd $AMBERHOME/AmberTools/benchmarks/nab;time ./bench_amber gcn4p1'
```

Or you can instantiate and enter the container
```
$ docker run -it indigodatacloudapps/ambertools-oneclient /bin/bash
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
