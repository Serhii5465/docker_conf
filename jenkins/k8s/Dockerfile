FROM jenkins/jenkins:2.467-jdk21

ARG DOCKER_GID

USER root

RUN apt update && apt install -y --no-install-recommends sudo nano iputils-ping curl \
    && curl -fsSL https://get.docker.com | sh \
    && groupmod -g ${DOCKER_GID} docker \
    && usermod -aG docker jenkins \
    && rm -rf /var/lib/apt/lists/* && apt-get clean \
    && echo "jenkins ALL=(ALL) NOPASSWD: ALL" >> /etc/sudoers \
    && curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl" \
    && install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl \
    && rm kubectl

USER jenkins