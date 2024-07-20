FROM rustlang/rust:nightly-alpine AS build





# Install host build dependencies.
#RUN apk add --no-cache clang lld musl-dev git pkgconfig perl make libressl-dev

# Build the application.
# Leverage a cache mount to /usr/local/cargo/registry/
# for downloaded dependencies, a cache mount to /usr/local/cargo/git/db
# for git repository dependencies, and a cache mount to /app/target/ for
# compiled dependencies which will speed up subsequent builds.
# Leverage a bind mount to the src directory to avoid having to copy the
# source code into the container. Once built, copy the executable to an
# output directory before the cache mounted /app/target is unmounted.
#RUN --mount=type=bind,source=src,target=src \
#    --mount=type=bind,source=public,target=public \
#    --mount=type=bind,source=assets,target=assets \
#    --mount=type=bind,source=Cargo.toml,target=Cargo.toml \
#    --mount=type=bind,source=Cargo.lock,target=Cargo.lock \
#    --mount=type=bind,source=Dioxus.toml,target=Dioxus.toml \
#    --mount=type=bind,source=input.css,target=input.css \
#    --mount=type=bind,source=tailwind.config.js,target=tailwind.config.js \
#    --mount=type=cache,target=/app/target/ \
#    --mount=type=cache,target=/usr/local/cargo/git/db \
#    --mount=type=cache,target=/usr/local/cargo/registry/ \
#cargo install dioxus-cli
#
#USER = jplummer01

#RUN rustup component add rustfmt
