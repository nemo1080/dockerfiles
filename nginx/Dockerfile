FROM ubuntu:24.04

RUN apt-get update \
    && apt-get install -y libpcre3 \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

COPY nginx.tar /usr/local/nginx.tar

RUN cd /usr/local \
    && tar -xf nginx.tar \
    && rm nginx.tar \
    && ln -s /usr/local/nginx/sbin/nginx /usr/local/bin/nginx

RUN mkdir -p /var/www/letsencrypt

VOLUME ["/usr/local/nginx/conf.d", "/usr/local/nginx/logs"]

EXPOSE 80 443

CMD ["/usr/local/bin/nginx"]