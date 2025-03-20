ARG BASE_IMAGE
FROM $BASE_IMAGE
ARG PULUMI_VERSION
ARG TARGETARCH

RUN echo "hosts: files dns" > /etc/nsswitch.conf \
  && adduser --disabled-password --uid=1983 spacelift

USER root
WORKDIR /home/spacelift
RUN apt-get update && apt-get install -y wget procps

RUN if [ "$TARGETARCH" = "arm64" ]; then \
    wget -q "https://get.pulumi.com/releases/sdk/pulumi-${PULUMI_VERSION}-linux-arm64.tar.gz" && \
    tar -xf pulumi-${PULUMI_VERSION}-linux-arm64.tar.gz; \
  else \
    wget -q "https://get.pulumi.com/releases/sdk/pulumi-${PULUMI_VERSION}-linux-x64.tar.gz" && \
    tar -xf pulumi-${PULUMI_VERSION}-linux-x64.tar.gz; \
  fi; \
  mv pulumi/* /usr/local/bin/; \
  rm -rf pulumi-${PULUMI_VERSION}*.tar.gz

USER spacelift
