FROM rtancman/php:5.6-fpm

RUN curl -sS https://getcomposer.org/installer | php \
&& mv composer.phar /usr/bin/composer \
&& wget psysh.org/psysh \
&& chmod +x psysh \
&& mv ./psysh /usr/bin/psysh \
&& wget https://phar.phpunit.de/phpunit.phar \
&& chmod +x phpunit.phar \
&& mv phpunit.phar /usr/local/bin/phpunit \
&& curl -LsS http://symfony.com/installer -o /usr/local/bin/symfony \
&& chmod a+x /usr/local/bin/symfony \
&& yes '' | pecl install -f xdebug \
&& echo "zend_extension=$(find /usr/local/lib/php/extensions/ -name xdebug.so)" > /usr/local/etc/php/conf.d/xdebug.ini \
&& echo "xdebug.remote_enable=on" >> /usr/local/etc/php/conf.d/xdebug.ini \
&& echo "xdebug.remote_handler=dbgp" >> /usr/local/etc/php/conf.d/xdebug.ini \
&& echo "xdebug.remote_connect_back=1" >> /usr/local/etc/php/conf.d/xdebug.ini \
&& echo "xdebug.remote_autostart=on" >> /usr/local/etc/php/conf.d/xdebug.ini \
&& echo "xdebug.remote_port=9004" >> /usr/local/etc/php/conf.d/xdebug.ini \
&& echo ";;;;;;;;;;;;;;;;;;; ; Module Settings ; ;;;;;;;;;;;;;;;;;;; \n\
[Date] \n\
; Defines the default timezone used by the date functions \n\
; http://www.php.net/manual/en/datetime.configuration.php#ini.date.timezone \n\
date.timezone = America/Sao_Paulo \n" >> /usr/local/etc/php/conf.d/datetimezone.ini \
&& rm -rf /var/lib/apt/lists/*

EXPOSE 9000

CMD ["php", "-a"]