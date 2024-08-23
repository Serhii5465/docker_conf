FROM jenkins/jenkins:alpine3.20-jdk21

USER root

ARG GID_DOCKER

RUN apk update && apk add --no-cache nano docker iputils-ping shadow \
    && groupmod -g ${GID_DOCKER} docker \
    && usermod -aG docker jenkins

WORKDIR /var/jenkins_home/

USER jenkins