FROM mcr.microsoft.com/devcontainers/base:trixie

# Install basic dependencies
RUN apt-get update && \
    apt-get install -y wget curl git jq apt-transport-https \
    bash unzip whois libssl-dev gnupg2 iputils-ping ca-certificates \
    && update-ca-certificates

# replace shell with bash so we can source files
RUN rm /bin/sh && ln -s /bin/bash /bin/sh

# Install project specific dependencies
RUN apt-get update && apt-get install -y build-essential

# Install project dependencies
RUN apt-get update && \
    apt-get install -y python3 python3-pip python3-venv pipx

# Cleanup.
RUN apt-get autoremove -y && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

ENTRYPOINT ["sleep", "infinity"]