ARG PHP_VERSION="8.2-fpm"
FROM php:8.2-fpm

RUN apt-get update
RUN apt-get upgrade -y
RUN apt-get install freetype-* -y
RUN apt-get install libedit-dev -y
RUN apt-get install libxml2  -y
RUN apt-get install libjpeg-dev -y
RUN apt-get install libpng-dev -y
RUN apt-get install mariadb-client -y
# RUN apt-get install wkhtmltopdf


RUN apt-get -y install gcc make autoconf libc-dev pkg-config
RUN apt-get install libmcrypt-dev -y
RUN apt-get install libzip-dev -y
RUN apt-get install libsodium-dev -y
RUN apt-get install curl -y
# RUN apt-get install openssl -y
# RUN apt-get install libssl-dev -y
# RUN pecl install mcrypt-1.0.1
# RUN apt-get install nodejs -y
# RUN apt-get install npm -y
# RUN apt-get install sqlite3 -y

#======PHP configure
RUN docker-php-ext-configure bcmath --enable-bcmath
RUN docker-php-ext-configure pdo_mysql --with-pdo-mysql
#RUN docker-php-ext-configure soap --enable-soap

#======PHP Extentions
RUN docker-php-ext-install gd
RUN docker-php-ext-install pdo
RUN docker-php-ext-install pdo_mysql
RUN docker-php-ext-install zip
RUN docker-php-ext-install mysqli
RUN docker-php-ext-install sodium
RUN docker-php-ext-install exif
RUN docker-php-ext-install iconv
# RUN docker-php-ext-install curl
# RUN docker-php-ext-install openssl
# RUN docker-php-ext-install png
# RUN docker-php-ext-install jpegn
# RUN docker-php-ext-install imagick
# RUN docker-php-ext-install intl
# RUN docker-php-ext-install pdo-mysql
# RUN docker-php-ext-install pdo_sqlite
# RUN docker-php-ext-install zlib
# RUN docker-php-ext-install json

RUN php -r "readfile('http://getcomposer.org/installer');" | php -- --install-dir=/usr/bin/ --filename=composer
#RUN chmod -R a+w /usr/local/apache2/htdocs/drupal8demo/web/sites/default/files
# RUN composer global require drush/drush:8.x
# RUN ln -s /root/.composer/vendor/drush/drush/drush /usr/bin/drush
RUN ln -s /root/.config/composer/vendor/drush/drush/drush /usr/bin/drush



#todo : add php configurable here...
#docker cp dstack_php:/usr/local/etc/php/php.ini php.ini
#todo : COPY  "php.ini" "$PHP_INI_DIR/php.ini"

RUN echo $PATH
# RUN echo ${PATH}


RUN apt-get install -y libpng-dev libfreetype6-dev libjpeg62-turbo-dev
# RUN docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/
RUN docker-php-ext-configure gd
RUN docker-php-ext-install -j$(nproc) gd



# RUN curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.3/install.sh | bash
# RUN export NVM_DIR="$([ -z "${XDG_CONFIG_HOME-}" ] && printf %s "${HOME}/.nvm" || printf %s "${XDG_CONFIG_HOME}/nvm")" [ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh" # This loads nvm