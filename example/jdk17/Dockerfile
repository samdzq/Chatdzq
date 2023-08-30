FROM ubuntu:18.04

RUN apt-get update && apt-get install -y locales && rm -rf /var/lib/apt/lists/*
RUN locale-gen en_US.UTF-8
ENV LANG en_US.UTF-8

ADD ./AliyunJavaAgent /usr/local/AliyunJavaAgent

ADD openlogic-openjdk-17.0.5+8-linux-x64.tar.gz /usr/local/
ENV JAVA_HOME /usr/local/openlogic-openjdk-17.0.5+8-linux-x64
ENV CLASSPATH $JAVA_HOME/lib/dt.jar:$JAVA_HOME/lib/tools.jar
ENV PATH $PATH:$JAVA_HOME/bin


