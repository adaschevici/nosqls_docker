FROM fedora:23
MAINTAINER Zero zero@localhost.com

RUN dnf -y update && dnf clean all
RUN dnf -y install redis && dnf clean all

EXPOSE 6379

CMD [ "redis-server" ]
