FROM debian:bookworm-slim

SHELL ["/bin/bash", "-o", "pipefail", "-c"]

ENV VITE_PLUS_HOME="/opt/viteplus"
ENV PATH="$VITE_PLUS_HOME/bin:$PATH"

WORKDIR /app

RUN apt-get update && \
	apt-get install -y --no-install-recommends ca-certificates curl && \
	curl -fsSL https://vite.plus/ | bash && \
	rm -rf /var/lib/apt/lists/*

CMD ["vp"]
