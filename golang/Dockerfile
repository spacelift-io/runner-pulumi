ARG REPOSITORY_BASE_PATH
ARG RELEASE_VERSION
FROM ${REPOSITORY_BASE_PATH}/runner-pulumi-base-alpine:${RELEASE_VERSION}

USER root
WORKDIR /home/spacelift

COPY --from=golang:1.19-alpine /usr/local/go/ /usr/local/go/
ENV PATH=${PATH}:/usr/local/go/bin

USER spacelift
