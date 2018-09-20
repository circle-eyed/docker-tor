FROM alpine:latest

LABEL maintainer="cyclops.zhao@protonmail.com"

RUN apk add --no-cache --update tor

COPY docker-entrypoint.sh /usr/local/bin/
RUN chmod +x /usr/local/bin/docker-entrypoint.sh \
 && ln -s /usr/local/bin/docker-entrypoint.sh / # backwards compat

VOLUME ["/etc/tor/torrc", "/var/lib/tor"]
EXPOSE 9050

USER tor

ENTRYPOINT ["docker-entrypoint.sh"]
