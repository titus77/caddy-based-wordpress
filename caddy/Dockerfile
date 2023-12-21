FROM caddy:2.7.5-builder-alpine AS builder

RUN xcaddy build \
    --with github.com/hairyhenderson/caddy-teapot-module \
    --with github.com/lucaslorentz/caddy-docker-proxy/v2 \
    --with github.com/caddy-dns/cloudflare \
    --with github.com/caddy-dns/ovh

FROM caddy:2.7.5

COPY --from=builder /usr/bin/caddy /usr/bin/caddy
