# docker基础镜像ubuntu添加jdk17

## 首先 pull ubuntu18.04

    docker pull ubuntu:18.04

## 下载jdk17


    openlogic-openjdk-17.0.5+8-linux-x64.tar.gz



## 创建Dockerfile文件

编写文件如下：


# 在ubuntu:18.04中添加上jdk17
    FROM ubuntu:18.04
    ADD openlogic-openjdk-17.0.5+8-linux-x64.tar.gz /usr/local/
    ENV JAVA_HOME /usr/local/openlogic-openjdk-17.0.5+8-linux-x64
    ENV CLASSPATH $JAVA_HOME/lib/dt.jar:$JAVA_HOME/lib/tools.jar
    ENV PATH $PATH:$JAVA_HOME/bin

用add命令添加的tar会自动解压，解压后的文件夹名为：openlogic-openjdk-17.0.5+8-linux-x64


# 构建过程：
    docker build -t dzq-ubuntu:jdk17 .


# 启动
    docker run -itd --name ubuntu-jdk17 \
    -d dzq-ubuntu:jdk17


# 进入容器
    docker exec -it ubuntu-jdk17 /bin/bash

## 查看环境
    javac
    java -version





