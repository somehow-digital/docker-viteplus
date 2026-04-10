FROM debian:bookworm-slim

SHELL ["/bin/bash", "-o", "pipefail", "-c"]

ARG VP_VERSION=0.1.16
ARG VP_NODE_MANAGER=yes

ENV VP_VERSION=${VP_VERSION}
ENV VP_HOME=/opt/viteplus
ENV VP_NODE_MANAGER=${VP_NODE_MANAGER}

WORKDIR /app

RUN apt-get update && \
	apt-get install -y --no-install-recommends ca-certificates curl git && \
	curl -fsSL https://vite.plus/ | bash && \
	chmod -R 777 ${VP_HOME} && \
	rm -rf /var/lib/apt/lists/*

ENV PATH="${VP_HOME}/bin:$PATH"

CMD ["vp"]
