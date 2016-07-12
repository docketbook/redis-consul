FROM redis:3.2.1-alpine

RUN set -x \
	&& apk add --no-cache --virtual .build-deps \
		make \
		openssl \
	&& wget -O containerpilot.tar.gz https://github.com/joyent/containerpilot/releases/download/2.1.2/containerpilot-2.1.2.tar.gz \
	&& tar -xzf containerpilot.tar.gz -C /usr/local/bin \
	&& rm -r containerpilot.tar.gz \
	&& apk del .build-deps

COPY redis-consul.json /etc/redis-consul.json
COPY redis.conf /usr/local/etc/redis/redis.conf
ENV CONTAINERPILOT=file:///etc/redis-consul.json

EXPOSE 6379
ENTRYPOINT [ "/usr/local/bin/containerpilot", "redis-server", "/usr/local/etc/redis/redis.conf"]