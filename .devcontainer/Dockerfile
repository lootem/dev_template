FROM mcr.microsoft.com/devcontainers/base:ubuntu

WORKDIR /src/app

# Install dependencies
RUN apt-get update && \
    apt-get install -y apt-transport-https python3 python3-pip python3-venv curl git jq software-properties-common unzip wget whois bash ca-certificates

RUN update-ca-certificates

# Cleanup.
RUN apt-get autoremove -y && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

ENV PATH="$HOME/.local/bin:$PATH"