FROM ubuntu:latest

ARG PORT=6969
ARG DIRECTORY=/srv/tftpboot

LABEL org.opencontainers.image.authors="rickmark@outlook.com"

RUN apt update; apt upgrade -y

RUN apt install -y tftpd-hpa

RUN mkdir -p ${DIRECTORY}

WORKDIR ${DIRECTORY}

EXPOSE 6969/udp

CMD [ "/usr/sbin/in.tftpd", "-L", "-v", "-c", "${DIRECTORY}", "-a", "0.0.0.0:${PORT}" ]