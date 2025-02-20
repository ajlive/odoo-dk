FROM caddy:2

ENV ENVIRONMENT=dev

ARG UID=900 GID=900

RUN addgroup --system --gid ${GID} caddy && \
    adduser --system --uid ${UID} --ingroup caddy caddy

RUN apk add --no-cache tzdata

COPY --chown=caddy:caddy /${ENVIRONMENT}.Caddyfile /etc/caddy/Caddyfile

RUN caddy validate --config /etc/caddy/Caddyfile

USER caddy

ENTRYPOINT ["caddy", "run", "--config", "/etc/caddy/Caddyfile", "--adapter", "caddyfile"]
