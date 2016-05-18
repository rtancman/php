FROM rtancman/php:5.6-fpm

# composer
RUN curl -sS https://getcomposer.org/installer | php
RUN mv composer.phar /usr/bin/composer

# psysh console php
RUN wget psysh.org/psysh
RUN chmod +x psysh
RUN mv ./psysh /usr/bin/psysh

# phpunit
RUN wget https://phar.phpunit.de/phpunit.phar
RUN chmod +x phpunit.phar
RUN mv phpunit.phar /usr/local/bin/phpunit

# symfony cli
RUN curl -LsS http://symfony.com/installer -o /usr/local/bin/symfony
RUN chmod a+x /usr/local/bin/symfony

RUN rm -rf /var/lib/apt/lists/*

EXPOSE 9000

CMD ["php", "-a"]