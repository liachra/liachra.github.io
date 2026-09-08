FROM fedora:44

# Install essential packages
RUN dnf -y install \
    git \
    golang \
    hugo \
    curl \
    tar \
    gzip \
    shadow-utils \
    sudo \
    ca-certificates \
    npm \
    && dnf clean all \
    && rm -rf /var/cache/dnf

# NPM global packages

# Create non-root user with sudo privileges
RUN useradd -m -s /bin/bash vscode \
    && echo "vscode ALL=(ALL) NOPASSWD:ALL" >> /etc/sudoers.d/vscode \
    && chmod 0440 /etc/sudoers.d/vscode

# Install Hugo Git
#RUN HUGO_VERSION=0.125.0 \
#    && curl -L -o /tmp/hugo.tar.gz "https://github.com/gohugoio/hugo/releases/download/v${HUGO_VERSION}/hugo_extended_${HUGO_VERSION}_Linux-64bit.tar.gz" \
#    && tar -xzf /tmp/hugo.tar.gz -C /tmp \
#    && install -m 755 /tmp/hugo /usr/local/bin/hugo \
#    && rm -rf /tmp/*
#USER vscode