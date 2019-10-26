FROM debian:stretch
MAINTAINER Roman Kozin
RUN apt-get update \
    && apt-get -y --yes install apt-utils vim apache2 php7.0-mysql libapache2-mod-php7.0 php7.0-curl php7.0-gd php7.0-imagick php7.0-json php7.0-mcrypt libapache2-mod-rpaf \
    && apt-get clean

ADD conf/mpm_prefork.conf /etc/apache2/mods-available/mpm_prefork.conf
ADD conf/rpaf.conf /etc/apache2/mods-available/rpaf.conf
ADD conf/vhost.conf /etc/apache2/sites-available/vhost.conf

RUN a2dissite 000-default.conf && a2ensite vhost.conf
RUN a2enmod rewrite && a2enmod rpaf

ENTRYPOINT ["/usr/sbin/apache2ctl", "-D", "FOREGROUND"]

EXPOSE 80 443
