ARG RELEASE_VERSION
ARG REPOSITORY_BASE_PATH

FROM ${REPOSITORY_BASE_PATH}/runner-pulumi-base-debian:${RELEASE_VERSION}

USER root

RUN apt-get update -y && \
    apt-get install -y git python3 python3-pip python3-dev && \
    ln -sf python3 /usr/bin/python && \
    pip3 install --no-cache --upgrade pip setuptools wheel

USER spacelift

ENV PATH="$PATH:./.pulumi/bin"
