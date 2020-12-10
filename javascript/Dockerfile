ARG RELEASE_VERSION

FROM ${REPOSITORY_BASE_PATH}/pulumi-base-alpine:${RELEASE_VERSION}

USER root
WORKDIR /home/spacelift
RUN apk add bash nodejs npm
USER spacelift
