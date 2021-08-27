FROM public.ecr.aws/spacelift/runner-terraform
ARG PULUMI_VERSION

USER root
WORKDIR /home/spacelift
RUN wget "https://get.pulumi.com/releases/sdk/pulumi-${PULUMI_VERSION}-linux-x64.tar.gz"
RUN tar -xf pulumi-${PULUMI_VERSION}-linux-x64.tar.gz
RUN mv pulumi/* /usr/local/bin/
USER spacelift
