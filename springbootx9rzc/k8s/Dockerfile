FROM registry.cn-shenzhen.aliyuncs.com/z_private/jdk:v8-alpine

LABEL MAINTAINER=springbootx9rzc

ENV NAME=springbootx9rzc

WORKDIR /$NAME
EXPOSE 8080

ARG JAR_FILE=target/$NAME.jar
COPY ${JAR_FILE} /$NAME/$NAME.jar

ENV TZ="Asia/Shanghai"
ENV JAVA_OPTS="-Xms256m -Xmx256m -Dfile.encoding=utf8 -Djava.security.egd=file:/dev/./urandom"
ENV PARAMS="-XX:+HeapDumpOnOutOfMemoryError -Xlog:gc*,:time,tags,level -XX:+UseZGC --server.port=8080"

ENTRYPOINT ["/bin/sh", "-c", "java ${JAVA_OPTS} -jar ${NAME}.jar ${PARAMS}"]