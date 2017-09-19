FROM debian:jessie

ENV LDAP_HOST 127.0.0.1
ENV LDAP_BASE_DN dc=ldap,dc=jpl
ENV LDAP_LOGIN_DN dc=admin,dc=ldap,dc=jpl
ENV LDAP_SERVER_NAME Ldap Jplsystemes

RUN apt-get update && apt-get install -y --no-install-recommends phpldapadmin
RUN apt-get remove -y apache2 php5 && apt-get -y autoremove

RUN rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

ADD config/config.php /etc/phpldapadmin/config.php
ADD config/apache.conf /etc/phpldapadmin/apache.conf
