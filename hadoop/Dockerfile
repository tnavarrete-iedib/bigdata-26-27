FROM ubuntu:24.04

ARG HADOOP_VERSION=3.5.0

ENV DEBIAN_FRONTEND=noninteractive

# Java 17 + eines bàsiques
RUN apt-get update && \
    apt-get install -y --no-install-recommends \
        openjdk-17-jdk \
        wget \
        curl \
        procps \
        iputils-ping \
        net-tools \
        bash \
        ca-certificates \
        && \
    rm -rf /var/lib/apt/lists/*

# Variables de Java i Hadoop
ENV JAVA_HOME=/usr/lib/jvm/java-17-openjdk-amd64
ENV HADOOP_HOME=/opt/hadoop
ENV HADOOP_CONF_DIR=/opt/hadoop/etc/hadoop
ENV PATH=${PATH}:${HADOOP_HOME}/bin:${HADOOP_HOME}/sbin

# Descarregar Hadoop
RUN wget -q \
    https://dlcdn.apache.org/hadoop/common/hadoop-${HADOOP_VERSION}/hadoop-${HADOOP_VERSION}.tar.gz \
    -O /tmp/hadoop.tar.gz && \
    tar -xzf /tmp/hadoop.tar.gz -C /opt && \
    mv /opt/hadoop-${HADOOP_VERSION} ${HADOOP_HOME} && \
    rm /tmp/hadoop.tar.gz

# Directoris utilitzats per HDFS
RUN mkdir -p /data/namenode /data/datanode

# Usuari per executar Hadoop
RUN groupmod --new-name hadoop ubuntu && \
    usermod --login hadoop --home /home/hadoop --move-home ubuntu && \
    chown -R hadoop:hadoop /opt/hadoop /data /home/hadoop

USER hadoop

WORKDIR /home/hadoop

CMD ["bash"] 
