ARG RELEASE_VERSION
ARG REPOSITORY_BASE_PATH

FROM golang:1.19-alpine3.16 as golang-source

FROM ${REPOSITORY_BASE_PATH}/runner-pulumi-base-alpine:${RELEASE_VERSION}
USER root
WORKDIR /home/spacelift
COPY --from=golang-source /usr/local/go /usr/local/go
ENV PATH=${PATH}:/usr/local/go/bin
USER spacelift
