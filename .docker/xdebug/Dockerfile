# Build the image once via CircleCI before running dev
# This adds uprofiler and xdebug on top of dev and adjusts opcache settings
FROM us.gcr.io/favish-general/aact-php

RUN pecl install \
xdebug-2.4.0 \
&& docker-php-ext-enable \
xdebug

# ZZ prefix to ensure configs are loaded after docker-ext configs added by the php container
COPY zz-xdebug.ini /usr/local/etc/php/conf.d/zz-xdebug.ini