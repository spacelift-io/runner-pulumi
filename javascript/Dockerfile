ARG RELEASE_VERSION
ARG REPOSITORY_BASE_PATH

FROM ${REPOSITORY_BASE_PATH}/pulumi-base-alpine:${RELEASE_VERSION}

USER root
WORKDIR /home/spacelift
RUN apk add bash nodejs npm
USER spacelift
