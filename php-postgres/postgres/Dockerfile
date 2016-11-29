FROM centos
MAINTAINER seike460

RUN yum update
RUN yum install -y http://yum.postgresql.org/9.4/redhat/rhel-7-x86_64/pgdg-centos94-9.4-1.noarch.rpm
RUN yum install -y postgresql94-server postgresql94-contrib enablerepo=pgdg94
USER postgres
RUN /usr/pgsql-9.4/bin/initdb --no-locale -E UTF8 -D /var/lib/pgsql/data
USER root

ENTRYPOINT /bin/systemctl start httpd.service \
  tail -f /var/log/message
