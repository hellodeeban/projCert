FROM projCert as vendor

WORKDIR /tmp/

RUN projCert install \
    --ignore-platform-reqs \
    --no-interaction \
    --no-plugins \
    --no-scripts \
    --prefer-dist


FROM php:7.2-apache-stretch

COPY . /var/www/html
COPY --from=vendor /tmp/vendor/ /var/www/html/vendor/
