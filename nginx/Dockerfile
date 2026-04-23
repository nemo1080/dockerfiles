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

VOLUME ["/usr/local/nginx/conf.d", "/app"]

EXPOSE 80 443

CMD ["/usr/local/bin/nginx"]