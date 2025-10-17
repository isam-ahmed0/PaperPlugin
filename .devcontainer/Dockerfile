# Use Ubuntu 22.04 as base
FROM ubuntu:22.04

# Avoid prompts
ENV DEBIAN_FRONTEND=noninteractive

# Install JDK 21
RUN apt-get update && \
    apt-get install -y wget unzip git curl maven && \
    wget https://github.com/adoptium/temurin21-binaries/releases/download/jdk-21.0.0+35/OpenJDK21U-jdk_x64_linux_hotspot_21.0.0_35.tar.gz -O /tmp/jdk21.tar.gz && \
    tar -xzf /tmp/jdk21.tar.gz -C /opt/ && \
    update-alternatives --install /usr/bin/java java /opt/jdk-21.0.0+35/bin/java 1 && \
    update-alternatives --install /usr/bin/javac javac /opt/jdk-21.0.0+35/bin/javac 1

# Set JAVA_HOME
ENV JAVA_HOME=/opt/jdk-21.0.0+35
ENV PATH=$JAVA_HOME/bin:$PATH

WORKDIR /workspace
