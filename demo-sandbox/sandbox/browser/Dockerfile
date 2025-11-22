FROM debian:bookworm-slim

RUN apt-get update && apt-get install -y \
    chromium \
    ca-certificates \
    curl \
    && useradd -m nonroot \
    && mkdir -p /home/nonroot/.config/chromium \
    && chown -R nonroot:nonroot /home/nonroot

WORKDIR /home/nonroot

COPY entrypoint.sh /usr/local/bin/entrypoint.sh
RUN chmod +x /usr/local/bin/entrypoint.sh

USER nonroot

ENTRYPOINT ["/usr/local/bin/entrypoint.sh"]
CMD ["chromium", "--headless", "--disable-gpu", "--no-sandbox"]