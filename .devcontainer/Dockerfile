FROM debian:bookworm-slim

RUN apt-get update

RUN apt-get install -y --no-install-recommends \
    g++ \
    gdb \
    clangd \
    clang-format

RUN apt-get install -y --no-install-recommends \
    python3 \
    python3-pip \
    python3-venv

RUN rm -rf /var/lib/apt/lists/*

RUN pip install --break-system-packages ruff ty

RUN ln -sf python3 /usr/bin/python

RUN mkdir -p /root/.config/clangd /workspaces
COPY config/clangd.yaml /root/.config/clangd/config.yaml
COPY config/clang-format /workspaces/.clang-format
