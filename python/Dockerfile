FROM alpine:3.9.4

RUN apk update \
    && apk add curl bash tree tzdata python python-dev py-pip \
    && apk add py-mysqldb build-base jpeg-dev zlib-dev libwebp-dev freetype-dev \
    && cp -r -f /usr/share/zoneinfo/Asia/Shanghai /etc/localtime \
    && pip install --upgrade pip \
    && pip install captcha Flask redis MySQL-python flask-cors regex \
    && rm -rf /var/cache/apk/*

