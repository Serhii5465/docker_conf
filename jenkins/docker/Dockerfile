FROM jenkins/jenkins:2.472-jdk21

USER root

RUN apt update && apt install -y --no-install-recommends nano iputils-ping \
    && rm -rf /var/lib/apt/lists/* && apt-get clean

USER jenkins