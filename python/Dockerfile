ARG REPOSITORY_BASE_PATH
ARG RELEASE_VERSION
FROM ${REPOSITORY_BASE_PATH}/runner-pulumi-base-debian:${RELEASE_VERSION}

USER root
RUN apt-get install -y git python3 python3-pip python3-dev python3-venv && ln -sf python3 /usr/bin/python
RUN pip3 install --no-cache --upgrade pip setuptools wheel
ENV PATH="$PATH:./.pulumi/bin"
USER spacelift
