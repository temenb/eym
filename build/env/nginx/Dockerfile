FROM nginx:1.14

ADD ./build/env/nginx/config/vhost.conf /etc/nginx/conf.d/default.conf

WORKDIR /var/www

#RUN usermod -u 1000 www-data