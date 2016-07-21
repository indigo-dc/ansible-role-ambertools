# docker build -t ambertools .

FROM indigodatacloud/ubuntu-sshd:14.04
MAINTAINER Mario David <mariojmdavid@gmail.com>
LABEL description="Container image to run AmberTools v16"

ENV AMBERHOME /usr/local/amber14
ENV PATH $PATH:/usr/lib64/openmpi/bin/:$AMBERHOME/bin
ENV LD_LIBRARY_PATH $AMBERHOME/lib
RUN ansible-galaxy install indigo-dc.ambertools && \
    ansible-playbook /etc/ansible/roles/indigo-dc.ambertools/tests/ambertools.yml

EXPOSE 22
CMD    ["/usr/sbin/sshd", "-D"]
