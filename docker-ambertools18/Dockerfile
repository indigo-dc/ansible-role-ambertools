# docker build --rm -t ambertools -f Dockerfile-amber-build .

FROM ubuntu:18.04
MAINTAINER Mario David <mariojmdavid@gmail.com>
LABEL description="Build Ambertools 18"

ENV AMBER_PREFIX="/usr/local/amber18"
ENV AMBERHOME="${AMBER_PREFIX}"
ENV PATH="${AMBER_PREFIX}/bin:${PATH}"
ENV LD_LIBRARY_PATH="${AMBER_PREFIX}/lib"

RUN apt update && \
    apt -y upgrade && \
    apt -y install \
      bzip2 \
      csh \
      flex \
      gfortran \
      g++ \
      libboost-dev \
      libboost-thread-dev \
      libboost-system-dev \
      libbz2-dev \
      libopenmpi-dev \
      make \
      openmpi-bin \
      patch \
      python3 \
      python3-dev \
      tar \
      xorg-dev \
      wget \
      zlib1g-dev && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/* && \
    update-alternatives --install /usr/bin/python python /usr/bin/python3 10 && \
    cd /usr/local && \
    wget http://www.lip.pt/~david/ambertools/AmberTools18.tar.bz2 && \
    tar -xvf AmberTools18.tar.bz2 && \
    rm -f AmberTools18.tar.bz2 && \
    cd ${AMBER_PREFIX} && \
    ./update_amber --update && \
    ./configure --with-python /usr/bin/python -noX11 -mpi gnu && \
    make install && \
    rm -rf ${AMBER_PREFIX}/doc \
           ${AMBER_PREFIX}/cmake \
           ${AMBER_PREFIX}/cmake-packaging \
           ${AMBER_PREFIX}/configure \
           ${AMBER_PREFIX}/logs \
           ${AMBER_PREFIX}/Makefile \
           ${AMBER_PREFIX}/share \
           ${AMBER_PREFIX}/src \
           ${AMBER_PREFIX}/AmberTools/src \
           ${AMBER_PREFIX}/AmberTools/test

