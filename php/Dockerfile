FROM alpine:3.20

RUN apk update && apk upgrade && \
    apk --no-cache add curl zip

RUN apk add php82 php82-fpm php82-mysqli

WORKDIR /home/app

RUN curl -O https://wordpress.org/wordpress-6.6.zip && \
    unzip wordpress-6.6.zip && \
    rm wordpress-6.6.zip && \
    mv wordpress/* ./ && \
    rmdir wordpress

VOLUME /home/app

RUN chown -R nobody:nobody /home/app

CMD ["php-fpm82", "-F"]
