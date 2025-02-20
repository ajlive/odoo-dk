FROM caddy:2

ENV ENVIRONMENT=dev

RUN apk add --no-cache tzdata

COPY --chown=caddy:caddy /${ENVIRONMENT}.Caddyfile /etc/caddy/Caddyfile

RUN caddy validate --config /etc/caddy/Caddyfile

USER caddy

ENTRYPOINT ["caddy", "run", "--config", "/etc/caddy/Ca