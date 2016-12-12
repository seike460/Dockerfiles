FROM ubuntu
MAINTAINER seike460

RUN apt-get update
RUN apt-get install -y python3
RUN apt-get install -y zsh
RUN apt-get install -y vim
RUN apt-get install -y python3-dev
RUN apt-get install -y python3-pip
RUN apt-get install -y nginx
RUN pip3 install -U pip
RUN pip3 install django uwsgi
RUN apt-get install -y mysql-client
RUN pip install virtualenv
RUN pip3 install PyMySQL

RUN ln -s /usr/bin/python3 /usr/bin/python

ENTRYPOINT /usr/src/app/manage.py runserver 0.0.0.0:80
