FROM nginx:1.14

ADD ./config/vhost.conf /etc/nginx/conf.d/default.conf

WORKDIR /var/www

#RUN usermod -u 1000 www-data