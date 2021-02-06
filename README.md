# docker-gradle-graalvm

## Introduction

Gradle can compile graalvm project in docker , ex : polyglot

## Get started

The docker images page : https://hub.docker.com/repository/docker/kirinddt/gradle-graalvm

docker cmd: ```kirinddt/gradle-graalvm:latest ```

## example

```Dockerfile
FROM kirinddt/gradle-graalvm:latest 

COPY . /app
WORKDIR /app
RUN java -version


RUN gradle :bzkflow:bootJar --refresh-dependencies 
#FROM springci/graalvm-ce:master-java11
RUN java -version
ENTRYPOINT ["java","-Dspring.profiles.active=prod","-cp","app:app/lib/*","net.bzk.flow.BzkflowApplication",">","/console.log"]
```
