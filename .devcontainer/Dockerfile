# .devcontainer/Dockerfile
FROM python:3.11-slim

# 基本的なツールのインストール
RUN apt-get update && apt-get install -y \
    git \
    && rm -rf /var/lib/apt/lists/*

# uvのインストール
RUN pip install uv

# uvを使ってruffをインストール
RUN uv pip install --system ruff

# 作業ディレクトリの設定
WORKDIR /workspace