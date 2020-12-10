ARG PULUMI_VERSION

FROM golang:1.15-alpine3.12 as golang-source

FROM quay.io/spacelift/dev-pulumi-base-alpine:${PULUMI_VERSION}
USER root
WORKDIR /home/spacelift
COPY --from=golang-source /usr/local/go /usr/local/go
ENV PATH=${PATH}:/usr/local/go/bin
USER spacelift
