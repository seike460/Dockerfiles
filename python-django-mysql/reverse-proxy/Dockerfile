FROM ubuntu
MAINTAINER seike460

RUN apt-get update
RUN apt-get install -y nginx

COPY ./default /etc/nginx/site-enabled/default

ENTRYPOINT  service nginx start && \
            tail -f /var/log/nginx/access.log
