FROM		alpine:3.18 AS base

RUN			apk add --update --virtual base \
				-X http://dl-cdn.alpinelinux.org/alpine/edge/main \
				postgresql16 \
				dumb-init && \
			rm -f /var/cache/apk/*


FROM		base AS packed

COPY		--chown=root:root entrypoint /run
STOPSIGNAL	SIGTERM
ENTRYPOINT	["dumb-init", "/run/entrypoint"]

