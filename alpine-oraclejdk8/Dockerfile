FROM alpine:3.9.4 AS builder

COPY jdk-8u211-linux-x64.tar.gz /tmp
ADD jce_policy-8.zip /tmp

RUN cd "/tmp" && \
    tar -xzf "jdk-8u211-linux-x64.tar.gz" && \
    unzip -jo -d "jdk1.8.0_211/jre/lib/security" "jce_policy-8.zip" && \
    cd "/tmp/jdk1.8.0_211" && \
    rm -rf *.zip *.txt jre/*.txt \
        "lib/missioncontrol" \
        "lib/visualvm" \
        "lib/"*javafx* \
        "jre/lib/plugin.jar" \
        "jre/lib/ext/jfxrt.jar" \
        "jre/bin/javaws" \
        "jre/lib/javaws.jar" \
        "jre/lib/desktop" \
        "jre/plugin" \
        "jre/lib/"deploy* \
        "jre/lib/"*javafx* \
        "jre/lib/"*jfx* \
        "jre/lib/amd64/libdecora_sse.so" \
        "jre/lib/amd64/"libprism_*.so \
        "jre/lib/amd64/libfxplugins.so" \
        "jre/lib/amd64/libglass.so" \
        "jre/lib/amd64/libgstreamer-lite.so" \
        "jre/lib/amd64/"libjavafx*.so \
        "jre/lib/amd64/"libjfx*.so \
        "jre/lib/security/README.txt"


FROM dolphintwo/alpine-cn:3.9.4
LABEL maintainer="dolphintwo <dtdinghui2@gmail.com>"
COPY --from=builder /tmp/jdk1.8.0_211 /usr/lib/jvm
RUN ln -s "/usr/lib/jvm/bin/"* "/usr/bin/" && \
    echo 'public class Main { public static void main(String[] args) { System.out.println("Java code is running fine!"); } }' > Main.java && \
    javac Main.java && \
    java Main
