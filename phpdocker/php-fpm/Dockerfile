FROM phpdockerio/php:8.3-fpm
WORKDIR "/application"

RUN apt-get update \
    && apt-get -y --no-install-recommends install \
        git \
        php8.3-gd \
        php8.3-mcrypt \
        php8.3-mysql \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /usr/share/doc/*

# Get NodeJS
COPY --from=node:22.11.0-slim /usr/local/bin /usr/local/bin
# Get npm
COPY --from=node:22.11.0-slim /usr/local/lib/node_modules /usr/local/lib/node_modules
