FROM nginx:stable-alpine

# Nginx configuration
RUN rm -rf /etc/nginx/conf.d/*
COPY keycloak.conf /etc/nginx/conf.d/keycloak.conf
COPY lets-encrypt.conf /etc/nginx/conf.d/lets-encrypt.conf

# Install certbot
RUN apk update && \
  apk add --no-cache certbot curl

# SSL configuration for Let's Encrypt
RUN mkdir -p /etc/letsencrypt
VOLUME /etc/letsencrypt

# Copy entrypoint.sh and provide permissions
COPY entrypoint.sh /custom/entrypoint.sh
RUN chmod +x /custom/entrypoint.sh

CMD ["/custom/entrypoint.sh"]
