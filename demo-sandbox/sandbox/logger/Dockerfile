FROM debian:bookworm-slim

RUN apt-get update && apt-get install -y tcpdump ca-certificates && rm -rf /var/lib/apt/lists/*

WORKDIR /logs

CMD ["tcpdump", "-i", "any", "-w", "/logs/traffic.pcap"]