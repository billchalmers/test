FROM nginx:latest

ENV DEBIAN_FRONTEND noninteractive

RUN apt-get update && apt-get install -y openssl apache2-utils

ADD https://raw.githubusercontent.com/billchalmers/test/master/nginx/entrypoint.sh /entrypoint.sh

RUN chmod 755 /entrypoint.sh

RUN apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

VOLUME ["/etc/nginx/conf.d"]

ENV NGINX_NAME="foo" \
    NGINX_PWD="bar"

ENTRYPOINT /entrypoint.sh