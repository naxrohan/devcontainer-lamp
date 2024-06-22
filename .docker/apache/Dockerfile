ARG APACHE_VERSION="latest"
FROM httpd:latest

RUN apt-get update
RUN apt-get upgrade -y



# Copy apache vhost file to proxy php requests to php-fpm container
COPY demo.apache.conf /usr/local/apache2/conf/demo.apache.conf
COPY ./ssl/server.crt /usr/local/apache2/conf/server.crt
COPY ./ssl/server.key /usr/local/apache2/conf/server.key
RUN echo "Include /usr/local/apache2/conf/demo.apache.conf" >> /usr/local/apache2/conf/httpd.conf
