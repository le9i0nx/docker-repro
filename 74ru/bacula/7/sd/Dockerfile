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
    mkdir /var/run/bacula/ && \
    chmod 0777 /var/run/bacula && \
    rm -rf /var/lib/apt/lists/*  /tmp/*
VOLUME ["/media", "/mnt", "/etc/bacula","/var/lib/bacula"]
EXPOSE 9104:9104
CMD ["sudo","-u","bacula","/usr/sbin/bacula-sd","-c","/etc/bacula/bacula7-sd.conf","-f"]
# docker pull le9i0nx/docker-repro:bacula7-sd
# docker run -d -v /etc/passwd:/etc/passwd:ro -v /etc/group:/etc/group:ro -v /etc/bacula:/etc/bacula:ro -v /mnt:/mnt:rw -v /media:/media:rw -v /var/lib/bacula:/var/lib/bacula:rw --name bacula7-sd le9i0nx/docker-repro:bacula7-sd
