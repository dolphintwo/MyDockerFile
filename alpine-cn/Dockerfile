FROM dolphintwo/alpine-glibc:3.9.4

RUN apk add --no-cache --virtual=build-dep ca-certificates wget && \
    echo @edge http://nl.alpinelinux.org/alpine/edge/testing >> /etc/apk/repositories && apk add wqy-zenhei@edge && \
    apk add wqy-zenhei --update-cache --repository http://nl.alpinelinux.org/alpine/edge/testing --allow-untrusted && \
    apk add --no-cache --update font-adobe-100dpi ttf-dejavu fontconfig tzdata && \
    cp -r -f /usr/share/zoneinfo/Asia/Shanghai /etc/localtime && \
    apk del build-dep && \
    rm -rf /var/cache/apk/*