FROM drupaldocker/php:cli

RUN apt-get update && apt-get install -y mysql-client unzip patch git \
  && composer global require drush/drush:6.* \
  && ln -s ~/.composer/vendor/bin/drush /usr/local/bin/drush \
  && drush core-status -y \
  && rm -rf /var/lib/apt/lists/*

CMD ["drush", "core-cli"]
