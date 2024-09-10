

FROM debian:10
RUN \
	apt -y update && \
	apt -y install apache2 && \
	apt -y install php php-cli php-common
	
RUN echo "Hello World" > /var/www/html/index.html
COPY server.crt /etc/ssl/certs/server.crt
COPY server.key /etc/ssl/private/server.key
COPY localhost-ssl.conf /etc/apache2/sites-available/tu-dominio-ssl.conf
RUN a2enmod ssl	


EXPOSE 443:443

CMD ["apachectl", "-D", "FOREGROUND"]


