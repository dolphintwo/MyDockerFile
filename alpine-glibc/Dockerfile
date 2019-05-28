FROM alpine:3.9.4

RUN apk add --no-cache --virtual=build-dep ca-certificates wget && \
    wget -q -O /etc/apk/keys/sgerrand.rsa.pub https://alpine-pkgs.sgerrand.com/sgerrand.rsa.pub && \
    wget https://github.com/sgerrand/alpine-pkg-glibc/releases/download/2.29-r0/glibc-2.29-r0.apk && \
    apk add glibc-2.29-r0.apk && \
    rm "/etc/apk/keys/sgerrand.rsa.pub" && \
    rm "glibc-2.29-r0.apk" && \
    rm "/root/.wget-hsts" && \
    rm -rf /var/cache/apk/* && \
    apk del build-dep
