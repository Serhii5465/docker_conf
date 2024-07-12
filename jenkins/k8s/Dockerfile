FROM jenkins/jenkins:2.467-jdk21

ARG DOCKER_GID

USER root

RUN apt update && apt install -y --no-install-recommends sudo nano iputils-ping curl \
    && curl -fsSL https://get.docker.com | sh \
    && groupmod -g ${DOCKER_GID} docker \
    && usermod -aG docker jenkins \
    && rm -rf /var/lib/apt/lists/* && apt-get clean \
    && echo "jenkins ALL=(ALL) NOPASSWD: ALL" >> /etc/sudoers 

USER jenkins