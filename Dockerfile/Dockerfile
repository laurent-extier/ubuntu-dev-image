FROM ubuntu

RUN useradd -s /bin/bash lex
RUN adduser lex sudo
RUN echo lex:isola2000 | chpasswd

RUN apt-get update && apt-get install sudo && apt-get install -y openssh-server

RUN mkdir -p /var/run/sshd

COPY ../config/ssh_config /etc/ssh/ssh_config

COPY ../scripts/start.sh /

EXPOSE 22

ENTRYPOINT [ "/start.sh" ]