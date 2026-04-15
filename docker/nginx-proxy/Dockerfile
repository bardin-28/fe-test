FROM nginxproxy/nginx-proxy:alpine

ARG BASIC_AUTH=false
ARG BASIC_AUTH_USERNAME=user
ARG BASIC_AUTH_PASSWORD=secret
ARG BASIC_AUTH_HOST=localhost

RUN if [ "${BASIC_AUTH}" = "true" ]; then set -ex; \
    mkdir -p "/etc/nginx/htpasswd"; \
    echo -n "$BASIC_AUTH_USERNAME:" >> "/etc/nginx/htpasswd/$BASIC_AUTH_HOST"; \
    echo "$BASIC_AUTH_PASSWORD" | openssl passwd -apr1 -stdin >> "/etc/nginx/htpasswd/$BASIC_AUTH_HOST"; \
fi