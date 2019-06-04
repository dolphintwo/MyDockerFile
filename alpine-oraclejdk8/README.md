# Alpine-oraclejdk:8u211

> oracle-jdk8含中文字体支持

## 下载地址

- [JDK8](https://oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)
- [JCE8](https://www.oracle.com/technetwork/java/javase/downloads/jce8-download-2133166.html)

## 构建

```shell
# oraclejdk
docker build -t dolphintwo/alpine-oraclejdk:8u211 .
# oraclejdk含中文字体支持
docker build -f Dockerfile-cntt -t dolphintwo/alpine-oraclejdk:8u211-cntt .
```

## 拉取

```shell
# oraclejdk
docker pull dolphintwo/alpine-oraclejdk:8u211
# oraclejdk含中文字体支持
docker pull dolphintwo/alpine-oraclejdk:8u211-cntt
```