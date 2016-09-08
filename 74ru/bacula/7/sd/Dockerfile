FROM ubuntu:16.04
MAINTAINER Aleksej Gavrilov <le9i0nx@gmail.com>
ENV LC_ALL C
ENV DEBIAN_FRONTEND noninteractive

RUN DEBIAN_FRONTEND=noninteractive \
    apt-get update  && \
    apt-get dist-upgrade -y && \
    apt-get install -y \
        sudo bacula-sd && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*  /tmp/*
VOLUME ["/media", "/mnt", "/etc/bacula"]
#ENTRYPOINT ["sudo -u bacula /usr/sbin/bacula-sd -c /etc/bacula/bacula-sd.conf -f"]
# docker run -d -p 9104:9103 -v /etc/bacula:/etc/bacula:ro -v /mnt:/mnt:rw -v /media:/media:rw --name bacula7-sd le9i0nx/docker-repro:bacula7-sd

