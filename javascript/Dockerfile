ARG PULUMI_VERSION

FROM quay.io/spacelift/dev-pulumi-base-alpine:${PULUMI_VERSION}

USER root
WORKDIR /home/spacelift
RUN apk add bash nodejs npm
USER spacelift
