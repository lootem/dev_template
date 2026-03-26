FROM mcr.microsoft.com/devcontainers/base:trixie

# Install basic dependencies
RUN apt-get update && \
    apt-get install -y wget curl git jq apt-transport-https \
    bash unzip whois libssl-dev gnupg2 iputils-ping ca-certificates \
    && update-ca-certificates

# replace shell with bash so we can source files
RUN rm /bin/sh && ln -s /bin/bash /bin/sh

# Install nvm and bun
USER vscode
ENV COREPACK_ENABLE_DOWNLOAD_PROMPT=0
RUN curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.3/install.sh | bash && \
    . /home/vscode/.nvm/nvm.sh && nvm install 24 && nvm alias default 24 && nvm use default && \
    npm install -g bun

# Cleanup
USER root
RUN apt-get autoremove -y && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

ENTRYPOINT ["sleep", "infinity"]