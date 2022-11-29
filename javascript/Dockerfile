ARG REPOSITORY_BASE_PATH
ARG RELEASE_VERSION
FROM ${REPOSITORY_BASE_PATH}/runner-pulumi-base-alpine:${RELEASE_VERSION}

USER root
WORKDIR /home/spacelift
RUN apk add bash nodejs npm
USER spacelift
