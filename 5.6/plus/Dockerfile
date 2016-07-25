FROM rtancman/php:5.6-fpm

# composer
# psysh console php
# phpunit
# symfony cli
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
    && rm -rf /var/lib/apt/lists/*

EXPOSE 9000

CMD ["php", "-a"]