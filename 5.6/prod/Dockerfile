
FROM bitnami/php-fpm:5.6.36-debian-8-r78 as development

FROM bitnami/minideb-runtimes:jessie-php
LABEL maintainer "Bitnami <containers@bitnami.com>"

COPY --from=development /opt/bitnami/common /opt/bitnami/common
COPY --from=development /opt/bitnami/php /opt/bitnami/php

ENV BITNAMI_APP_NAME="php-fpm" \
    BITNAMI_IMAGE_VERSION="5.6.36-debian-8-r78" \
    PATH="/opt/bitnami/php/bin:/opt/bitnami/php/sbin:/opt/bitnami/php/sbin:$PATH"

CMD ["php-fpm","-F","--pid","/opt/bitnami/php/tmp/php-fpm.pid","-y","/opt/bitnami/php/etc/php-fpm.conf"]
