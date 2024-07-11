FROM jenkins/jenkins:2.467-jdk21

USER root

RUN apt update && apt install -y --no-install-recommends sudo nano iputils-ping \
    && rm -rf /var/lib/apt/lists/* && apt-get clean \
    && echo "jenkins ALL=(ALL) NOPASSWD: ALL" >> /etc/sudoers 

USER jenkins