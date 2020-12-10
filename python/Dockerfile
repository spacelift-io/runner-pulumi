ARG RELEASE_VERSION

FROM ${REPOSITORY_BASE_PATH}/pulumi-base-debian:${RELEASE_VERSION}

USER root
RUN apt-get install -y python3 python3-pip python3-dev && ln -sf python3 /usr/bin/python
RUN pip3 install --no-cache --upgrade pip setuptools wheel
USER spacelift
ENV PATH="$PATH:./.pulumi/bin"
