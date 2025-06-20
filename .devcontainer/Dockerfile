FROM rust:latest

# Install Solana CLI
RUN sh -c "$(curl -sSfL https://release.solana.com/stable/install)" && \
    echo 'export PATH="/root/.local/share/solana/install/active_release/bin:$PATH"' >> /root/.bashrc

# Install Anchor CLI
RUN apt-get update && \
    apt-get install -y pkg-config libssl-dev libudev-dev libclang-dev cmake build-essential curl git && \
    cargo install --git https://github.com/coral-xyz/anchor anchor-cli --locked

# Set up Node.js and Yarn
RUN curl -fsSL https://deb.nodesource.com/setup_20.x | bash - && \
    apt-get install -y nodejs && npm install -g yarn

# Set environment variables
ENV PATH="/root/.cargo/bin:/root/.local/share/solana/install/active_release/bin:$PATH"
