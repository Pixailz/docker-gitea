FROM		alpine:latest AS base

RUN			apk add --update --virtual base \
				gitea \
				dumb-init \
				openssh-client && \
			rm -f /var/cache/apk/*


FROM		base AS packed

COPY		--chown=root:root entrypoint /run
ENTRYPOINT	["dumb-init", "/run/entrypoint"]
