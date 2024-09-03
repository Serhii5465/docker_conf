FROM portainer/portainer-ce:2.21.0-alpine

ARG USER_NAME
ARG USER_ID
ARG DOCKER_GID

ENV TZ=Europe/Kyiv

RUN apk add --no-cache tzdata \ 
    && cp /usr/share/zoneinfo/${TZ} /etc/localtime \
    && addgroup -g ${DOCKER_GID} docker \  
    && adduser --uid ${USER_ID} --shell /bin/sh --ingroup docker --no-create-home --disabled-password ${USER_NAME} \
    && mkdir -p /data && chown -R ${USER_NAME} /data

USER ${USER_NAME}

WORKDIR /home/${USER_NAME}
