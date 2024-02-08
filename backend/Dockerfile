# 開発環境
FROM rust:buster
WORKDIR /app
RUN cargo init
COPY Cargo.toml /backebd/Cargo.toml
RUN cargo fetch
COPY . .
RUN apt-get update
RUN cargo install cargo-watch