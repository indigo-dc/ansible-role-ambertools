# docker build --rm -t ambertools-oneclient .
FROM lipcomputing/ansible-ubuntu16.04
MAINTAINER Mario David <mariojmdavid@gmail.com>
LABEL description="Container image to run AmberTools v17. Installed Oneclient"

ENV AMBERHOME /usr/local/amber16
ENV PATH $PATH:AMBERHOME/bin
ENV LD_LIBRARY_PATH $AMBERHOME/lib
RUN apt-get update && apt-get -y install openjdk-8-jdk maven
RUN ansible-galaxy install indigo-dc.oneclient &&\
    ansible-galaxy install git+https://github.com/indigo-dc/ansible-role-ambertools.git && \
    ansible-playbook /etc/ansible/roles/indigo-dc.oneclient/tests/test.yml && \
    ansible-playbook /etc/ansible/roles/ansible-role-ambertools/tests/ambertools.yml
