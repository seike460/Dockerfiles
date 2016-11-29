FROM centos
MAINTAINER seike460

RUN yum update
RUN yum install -y http://rpms.famillecollet.com/enterprise/remi-release-7.rpm
RUN yum install -y \
httpd \
httpd-devel \
php70 \
php70-php \
php70-php-devel \
php70-php-xml \
php70-php-mbstring \
php70-php-gd \
php70-php-pgsql \
php70-php-mysqlnd \
php70-php-mcrypt \
php70-php-intl \
php70-php-opcache \
php70-php-pdo \
php70-php-json \
php70-php-pecl-zip

ENTRYPOINT ["/bin/systemctl", "start", "httpd.service"]
