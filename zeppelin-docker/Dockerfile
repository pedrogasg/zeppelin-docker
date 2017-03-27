FROM ubuntu:14.04

RUN apt-get -y update
RUN apt-get -y install curl

# JAVA

ARG JAVA_ARCHIVE=http://download.oracle.com/otn-pub/java/jdk/8u102-b14/server-jre-8u102-linux-x64.tar.gz

ENV JAVA_HOME /usr/local/jdk1.8.0_102

ENV PATH $PATH:$JAVA_HOME/bin
RUN curl -sL --retry 3 --insecure \
  --header "Cookie: oraclelicense=accept-securebackup-cookie;" ${JAVA_ARCHIVE} \
  | tar -xz -C /usr/local/ && ln -s $JAVA_HOME /usr/local/java 

# ZEPPELIN

ARG ZEPPELIN_ARCHIVE=https://archive.apache.org/dist/zeppelin/zeppelin-0.6.2/zeppelin-0.6.2-bin-all.tgz

ENV ZEPPELIN_HOME /usr/local/zeppelin-0.6.2-bin-all

ENV PATH $PATH:${ZEPPELIN_HOME}/bin

RUN curl -s ${ZEPPELIN_ARCHIVE} | tar -xz -C /usr/local/

WORKDIR $ZEPPELIN_HOME

CMD ["/bin/bash"]
