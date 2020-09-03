FROM wordpress:php7.4-apache
COPY wp-redis.ini /usr/local/etc/php/conf.d/
RUN yes no | pecl install redis \
&& rm -rf /tmp/pear \
&& docker-php-ext-enable redis
