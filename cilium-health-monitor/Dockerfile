FROM quay.io/cilium/cilium-cli:v0.20.1 AS cilium
FROM debian:13-slim

RUN apt-get update \
 && apt-get install -y --no-install-recommends \
      bash \
      ca-certificates \
      curl \
      jq \
 && rm -rf /var/lib/apt/lists/*

# Install cilium cli
COPY --from=cilium /usr/local/bin/cilium /usr/local/bin/cilium

WORKDIR /work

ENTRYPOINT ["/scripts/monitor.sh"]
