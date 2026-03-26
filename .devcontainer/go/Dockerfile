FROM mcr.microsoft.com/devcontainers/base:trixie

# Update as needed https://go.dev/dl/
ARG GO_URL=https://go.dev/dl/go1.26.1.linux-amd64.tar.gz

# Install basic dependencies
RUN apt-get update && \
    apt-get install -y wget curl git jq apt-transport-https \
    bash unzip whois libssl-dev gnupg2 iputils-ping ca-certificates \
    && update-ca-certificates

# replace shell with bash so we can source files
RUN rm /bin/sh && ln -s /bin/bash /bin/sh

# Install project specific dependencies
RUN apt-get update && \
    apt-get install -y build-essential

# Install Go
RUN curl -fsSL "${GO_URL}" | tar -xz -C /usr/local
ENV PATH="/usr/local/go/bin:${PATH}"
RUN go version

# Cleanup
RUN apt-get autoremove -y && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

ENTRYPOINT ["sleep", "infinity"]