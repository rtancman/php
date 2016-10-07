FROM php:5.6-fpm-dev

RUN yes '' | pecl install -f memcache \
    && echo "extension=memcache.so" >> /usr/local/etc/php/conf.d/memcache.ini \
    && wget https://launchpad.net/libmemcached/1.0/1.0.18/+download/libmemcached-1.0.18.tar.gz \
    && tar xzf libmemcached-1.0.18.tar.gz \
    && rm -f libmemcached-1.0.18.tar.gz \
    && ./libmemcached-1.0.18/configure --enable-sasl \
    && make install \
    && yes '' | pecl install -f memcached \
    && echo "extension=memcached.so" >> /usr/local/etc/php/conf.d/memcached.ini

EXPOSE 9000

CMD ["php", "-a"]
