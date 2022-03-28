FROM php:7.4-cli

RUN apt update \
    && apt install -y zlib1g-dev g++ git libicu-dev zip libzip-dev zip npm \
    && docker-php-ext-install intl opcache pdo pdo_mysql xsl \
    && pecl install apcu \
    && docker-php-ext-enable apcu \
    && docker-php-ext-install zip \
    && docker-php-ext-configure zip

WORKDIR /var/www/symfony_projects

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

RUN curl -sS https://get.symfony.com/cli/installer | bash
RUN mv /root/.symfony/bin/symfony /usr/local/bin/symfony
RUN git config --global user.email "jffranck@wideagency.com" \ 
    && git config --global user.name "Jean-François FRANCK"
