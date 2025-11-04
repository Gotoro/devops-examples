# Stage 1: Build the custom Caddy binary
FROM caddy:2.10.2-builder-alpine AS builder

RUN xcaddy build \
    --with github.com/mholt/caddy-l4 

# Stage 2: Create the final, lightweight image
FROM caddy:2.10.2-alpine

# Copy the custom-built Caddy binary from the builder stage
COPY --from=builder /usr/bin/caddy /usr/bin/caddy
