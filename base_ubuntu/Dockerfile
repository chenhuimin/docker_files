FROM ubuntu:14.10
MAINTAINER Huimin Chen "349196770@qq.com"
ENV REFRESHED_AT 2015-08-08

RUN mv /etc/apt/sources.list /etc/apt/sources.list.bak
ADD sources.list /etc/apt/sources.list

RUN apt-get update

RUN apt-get install -y man dos2unix openssh-server supervisor

#update root password
RUN echo "root:root" | chpasswd

RUN mkdir -p /var/run/sshd
RUN mkdir -p /var/log/supervisor

COPY supervisord.conf /etc/supervisor/conf.d/supervisord.conf

EXPOSE 22

CMD ["/usr/bin/supervisord"]