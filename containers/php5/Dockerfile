FROM octohost/php5

RUN echo "<?php phpinfo(); ?>" > /srv/www/phpinfo.php
ADD ./index.php /srv/www/

RUN apt-get update && \
    apt-get -yq install php5-dev && \
    pecl install mongo

ADD ./php.ini /etc/php5/fpm/
ADD ./default /etc/nginx/sites-available/default

EXPOSE 80

CMD service php5-fpm start && nginx