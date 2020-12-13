FROM ubuntu

RUN useradd -s /bin/bash --create-home --home /home/lex/ lex
RUN adduser lex sudo
RUN echo lex:isola2000 | chpasswd
RUN echo "export DOCKER_HOST=tcp://10.0.2.15:2376" >> /home/lex/.bashrc
RUN mkdir -p /home/lex/data

RUN apt-get update && apt-get install sudo -y && apt-get install openssh-server -y && apt-get install vim -y && apt-get install dnsutils -y && apt-get install iputils-ping -y && apt-get install docker.io -y &&

RUN mkdir -p /var/run/sshd

COPY ssh_config /etc/ssh/ssh_config

COPY start.sh /

EXPOSE 22

ENTRYPOINT [ "/start.sh" ]
