# 開発環境
FROM rust:alpine

WORKDIR /app

# キャッシュを最大限活用するために、apk updateとapk addを1つのRUNコマンドにまとめる
RUN apk update && \
    apk add --no-cache alpine-sdk

# cargo-watchのバージョンを指定してインストール
RUN cargo install cargo-watch

# 依存関係のファイルのみをコピーしてキャッシュを有効にする
COPY Cargo.toml Cargo.lock ./
COPY . .
RUN cargo build

RUN cargo fetch

# アプリケーションのコードを追加


# その他のビルドステップを追加
RUN rustup component add rustfmt