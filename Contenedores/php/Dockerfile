FROM php:8.0-fpm

WORKDIR /var/www/html

COPY index.php .

RUN apt-get update && apt-get install -y curl libcurl4-openssl-dev libssl-dev libpq-dev

#RUN curl -sS https://getcomposer.org/installer -o composer-setup.php && php composer-setup.php --install-dir=/usr/local/bin/composer
#RUN composer install --no-dev --prefer-dist
#RUN sed -i 's/;DirectoryIndex /DirectoryIndex/' /etc/nginx/nginx.conf
#RUN sed -i 's/;ServerName /ServerName/' /etc/nginx/nginx.conf

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]