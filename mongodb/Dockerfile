FROM fedora:23
MAINTAINER Zero zero@localhost.com

#COMMENT { "description": "mongodb service container", \ 
#          "usage": "docker run -d -p 27017:27017 --name mongodb mlamouri/mongodb --volume=/mydbdatadir:/var/lib/mongodb" }

RUN  dnf install -y mongodb-server && dnf clean all

# RUN  mkdir -p /data && \
#      touch /var/lib/mongodb/.keep && \
#      chown -R mongodb:mongodb /var/lib/mongodb

ADD mongodb.conf /etc/mongodb.conf

# VOLUME [ "/var/lib/mongodb" ]

EXPOSE 27017

RUN mkdir /data
RUN mkdir /data/mongodb
RUN mkdir /data/logs

RUN chown mongodb /data
RUN chown mongodb /data/mongodb
RUN chown mongodb /data/logs


USER mongodb


WORKDIR /data/mongodb

ENTRYPOINT ["/usr/bin/mongod", "--config", "/etc/mongodb.conf"]
