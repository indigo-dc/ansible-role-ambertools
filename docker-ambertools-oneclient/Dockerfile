# docker build -t ambertools-oneclient .
FROM ubuntu:14.04
MAINTAINER Mario David <mariojmdavid@gmail.com>
LABEL description="Container image to run AmberTools v16. Installed Oneclient"

# Install ansible repository
RUN locale-gen en_US.UTF-8
RUN apt-get update -y
RUN apt-get install software-properties-common -y
RUN apt-add-repository ppa:ansible/ansible -y
RUN apt-get update && apt-get install -y \
    ansible

ENV AMBERHOME /usr/local/amber16
ENV PATH $PATH:/usr/lib64/openmpi/bin/:$AMBERHOME/bin
ENV LD_LIBRARY_PATH $AMBERHOME/lib
RUN ansible-galaxy install indigo-dc.oneclient indigo-dc.ambertools && \
    ansible-playbook \
        -i /etc/ansible/roles/indigo-dc.ambertools/tests/inventory \
        /etc/ansible/roles/indigo-dc.oneclient/tests/test.yml && \
    ansible-playbook \
        -i /etc/ansible/roles/indigo-dc.ambertools/tests/inventory \
        /etc/ansible/roles/indigo-dc.ambertools/tests/ambertools.yml
