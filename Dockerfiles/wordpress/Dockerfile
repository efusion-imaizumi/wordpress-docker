FROM wordpress:5.0.3-php7.2-apache

ADD ssl.conf /etc/apache2/sites-available/ssl.conf
ADD endpoint.sh /opt/endpoint.sh

RUN chmod a+x /opt/endpoint.sh
RUN /bin/bash -c "source /opt/endpoint.sh /etc/apache2/ssl_keys localhost"
RUN a2enmod ssl
RUN a2ensite ssl

#CMD ["/usr/sbin/apache2ctl", "-D", "FOREGROUND"]
CMD bash -c "chmod -R 777 /var/www/html/wp-content/plugin/wp-all-import-pro && /usr/sbin/apache2ctl -D FOREGROUND"
CMD ["/usr/sbin/apache2ctl", "-D", "FOREGROUND"]
