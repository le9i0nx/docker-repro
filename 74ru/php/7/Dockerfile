FROM ubuntu:16.04
MAINTAINER Aleksej Gavrilov <le9i0nx@gmail.com>
ENV LC_ALL C
ENV DEBIAN_FRONTEND noninteractive

RUN DEBIAN_FRONTEND=noninteractive \
    apt-get update  && \
    apt-get dist-upgrade -y && \
    apt-get install -y \
        sudo php7.0-fpm && \
    apt-get clean && \
    mkdir /srv/www && \
    rm -rf /var/lib/apt/lists/*  /tmp/*
VOLUME ["/srv/www","/run"]
CMD ["/usr/sbin/php-fpm7.0", "-F", "-O"]
# docker pull le9i0nx/docker-repro:php7-fpm
# docker run -d /srv/www:/srv/www:ro --name php7-fpm le9i0nx/docker-repro:php7-fpm
