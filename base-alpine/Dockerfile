FROM public.ecr.aws/spacelift/runner-terraform
ARG PULUMI_VERSION
ARG TARGETARCH

USER root
WORKDIR /home/spacelift

RUN if [ "$TARGETARCH" = "amd64" ]; then \
    wget -q "https://get.pulumi.com/releases/sdk/pulumi-${PULUMI_VERSION}-linux-x64.tar.gz" && \
    tar -xf pulumi-${PULUMI_VERSION}-linux-x64.tar.gz; \
  else \
    wget -q "https://get.pulumi.com/releases/sdk/pulumi-${PULUMI_VERSION}-linux-arm64.tar.gz" && \
    tar -xf pulumi-${PULUMI_VERSION}-linux-arm64.tar.gz; \
  fi; \
  mv pulumi/* /usr/local/bin/; \
  rm -rf pulumi-${PULUMI_VERSION}*.tar.gz

USER spacelift
