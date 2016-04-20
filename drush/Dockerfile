# Drush Docker Container
FROM dgtlmoon/composer
MAINTAINER Eksponent <info@eksponent.com>

# Add common extensions
RUN apt-get update && apt-get install -y mysql-client
RUN docker-php-ext-install pdo_mysql

# Drush 6 needs the Console_Table pear.
RUN pear install Console_Table

# Set the Drush version.
ENV DRUSH_VERSION 6.7.0

# Install Drush using Composer.
RUN composer global require drush/drush:"$DRUSH_VERSION" --prefer-dist

# Add the Redis PHP module.
#RUN git clone --branch="php5" https://github.com/phpredis/phpredis.git /usr/src/php/ext/redis && \
#  # Install the Redis module.
#  docker-php-ext-install redis && \
#  # Test to make sure it's available.
#  php -m && php -r "new Redis();"

# Update the entry point of the application
ENTRYPOINT ["drush"]
