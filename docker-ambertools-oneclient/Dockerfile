# docker build --rm -t ambertools-oneclient .
FROM lipcomputing/ansible-ubuntu14.04
MAINTAINER Mario David <mariojmdavid@gmail.com>
LABEL description="Container image to run AmberTools v16. Installed Oneclient"

ENV AMBERHOME /usr/local/amber16
ENV PATH $PATH:/usr/lib64/openmpi/bin/:$AMBERHOME/bin
ENV LD_LIBRARY_PATH $AMBERHOME/lib
RUN ansible-galaxy install indigo-dc.oneclient indigo-dc.ambertools && \
    ansible-playbook /etc/ansible/roles/indigo-dc.oneclient/tests/test.yml && \
    ansible-playbook /etc/ansible/roles/indigo-dc.ambertools/tests/ambertools.yml
