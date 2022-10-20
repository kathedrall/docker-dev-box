FROM debian:latest
RUN apt-get update
RUN apt-get install -y openssh-server openssh-client 

RUN if [ ! -f /tmp/id_rsa ] ; then  ssh-keygen -q  -t   rsa -b 4096 -C 'dev@dev'  -f /tmp/id_rsa ; fi 

