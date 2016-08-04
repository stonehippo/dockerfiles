FROM php:5.5-cli
MAINTAINER George White <stonehippo@gmail.com>

# create a non-priveleged user
RUN groupadd -r pl2 \
    && useradd -r -g pl2 pl2 \
    && mkdir /home/pl2 \
    && chown pl2 /home/pl2 \
    && chgrp pl2 /home/pl2

RUN apt-get update \
    && apt-get install -y zip \
        git

COPY php.ini /usr/local/etc/php/

# Install Composer dependency https://getcomposer.org/download/
RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
RUN php -r "if (hash_file('SHA384', 'composer-setup.php') === 'e115a8dc7871f15d853148a7fbac7da27d6c0030b848d9b3dc09e2a0388afed865e6a3d6b3c0fad45c48e2b5fc1196ae') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"
RUN php composer-setup.php
RUN php -r "unlink('composer-setup.php');"

# make Composer global
RUN mv composer.phar /usr/local/bin/composer

RUN chmod o+w /opt

USER pl2

# Create a default Pattern Lab project
RUN composer create-project pattern-lab/edition-mustache-standard \
    /opt/pattern-lab

# Make Pattern Lab source files available for modification
WORKDIR /opt/pattern-lab
VOLUME /opt/pattern-lab/source

CMD ["php", "core/console", "--server", "--host", "0.0.0.0", "--port", "8080", "--with-watch"]

EXPOSE 8080
