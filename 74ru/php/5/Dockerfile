FROM ubuntu:14.04
MAINTAINER Aleksej Gavrilov <le9i0nx@gmail.com>
ENV LC_ALL C
ENV DEBIAN_FRONTEND noninteractive

RUN DEBIAN_FRONTEND=noninteractive \
    apt-get update  && \
    apt-get dist-upgrade -y && \
    apt-get install -y \
        sudo php5-fpm && \
    apt-get clean && \
    mkdir /srv/www && \
    rm -rf /var/lib/apt/lists/*  /tmp/*
VOLUME ["/srv/www"]
CMD /usr/sbin/php5-fpm -F -O
# docker pull le9i0nx/docker-repro:php5-fpm
# docker run -i -v /srv/www:/srv/www:ro -v /run/php5:/run/php:rw --name php5-fpm le9i0nx/docker-repro:php5-fpm
