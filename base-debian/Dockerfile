ARG BASE_IMAGE=debian:latest
FROM $BASE_IMAGE
ARG PULUMI_VERSION
ARG TARGETARCH

RUN echo "hosts: files dns" > /etc/nsswitch.conf \
  && useradd --create-home --shell /bin/bash --uid 1983 spacelift

USER root
WORKDIR /home/spacelift

# The FIPS base image installs fips.so outside the Debian OpenSSL modules directory.
# Without an explicit module path, OpenSSL loads only the base provider and has no digests.
RUN if [ -f /usr/ssl/fipsmodule.cnf ] && ! grep -q "^module *=" /usr/ssl/fipsmodule.cnf; then \
    sed -i "/^\[fips_sect\]/a module = /usr/lib/ossl-modules/fips.so" /usr/ssl/fipsmodule.cnf; \
  fi

RUN apt-get update && apt-get install -y wget procps

RUN if [ "$TARGETARCH" = "arm64" ]; then \
    wget -q "https://get.pulumi.com/releases/sdk/pulumi-${PULUMI_VERSION}-linux-arm64.tar.gz" && \
    tar -xf pulumi-${PULUMI_VERSION}-linux-arm64.tar.gz; \
  else \
    wget -q "https://get.pulumi.com/releases/sdk/pulumi-${PULUMI_VERSION}-linux-x64.tar.gz" && \
    tar -xf pulumi-${PULUMI_VERSION}-linux-x64.tar.gz; \
  fi && \
  mv pulumi/* /usr/local/bin/ && \
  rm -rf pulumi-${PULUMI_VERSION}*.tar.gz

USER spacelift
