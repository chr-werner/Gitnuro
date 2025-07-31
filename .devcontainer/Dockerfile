FROM debian:bookworm-20250721

# Metadata
LABEL maintainer="Christoph Werner"
LABEL version="1.0.0"
LABEL build-date="2025-07-30"
LABEL description="Multi-language development environment with Java 24, Rust, and Perl"

# Set environment variables
ENV DEBIAN_FRONTEND=noninteractive

# Install system dependencies
RUN apt-get update && apt-get install -y \
    curl \
    wget \
    git \
    build-essential \
    pkg-config \
    libssl-dev \
    ca-certificates \
    openssl \
    cmake \
    gnupg \
    htop \
    tree \
    procps \
    sudo \
    perl \
    perl-modules \
    libperl-dev \
    cpanminus \
    unzip \
    libssh-4 \
    gcc-aarch64-linux-gnu \
    libgl1 \
    libfontconfig1 \
    fontconfig \
    libgl1 \
    libgl1-mesa-dri \
    libxrender1 \
    libxtst6 \
    libxi6 \
    && rm -rf /var/lib/apt/lists/*

# Create a non-root user
RUN groupadd --gid 1000 dev \
    && useradd --uid 1000 --gid dev --shell /bin/bash --create-home dev \
    && echo dev ALL=\(root\) NOPASSWD:ALL > /etc/sudoers.d/dev \
    && chmod 0440 /etc/sudoers.d/dev

USER dev

# # Set Rust environment variables for dev user
# ENV RUSTUP_HOME=/home/dev/.rustup
# ENV CARGO_HOME=/home/dev/.cargo
# ENV PATH=$CARGO_HOME/bin:$PATH

# # Install Rust and cargo-kotars for dev user
# RUN curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh -s -- -y --default-toolchain stable \
#     && rustup target add aarch64-unknown-linux-gnu \
#     && cargo install cargo-kotars --git https://github.com/JetpackDuba/kotars


# Set working directory
WORKDIR /workspace
