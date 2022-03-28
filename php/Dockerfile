FROM php:8.1-cli

RUN echo 'deb [trusted=yes] https://repo.symfony.com/apt/ /' | tee /etc/apt/sources.list.d/symfony-cli.list \
	&& apt update \
    && apt install -y zlib1g-dev g++ git libicu-dev libxslt1-dev libzip-dev zip npm \
	&& apt install symfony-cli \
    && docker-php-ext-install intl opcache pdo pdo_mysql xsl \
    && pecl install apcu \
    && docker-php-ext-enable apcu \
    && docker-php-ext-install zip \
    && docker-php-ext-configure zip

WORKDIR /var/www/symfony_projects

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

RUN git config --global user.email "jffranck@wideagency.com" \ 
    && git config --global user.name "Jean-François FRANCK"
