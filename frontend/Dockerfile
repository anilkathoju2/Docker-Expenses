FROM nginx:mainline-alpine3.20-slim

RUN rm -rf /etc/nginx/nginx.conf \
    && rm -rf /etc/nginx/conf.d/default.conf \
    && mkdir -p /var/cache/nginx \
    && chown -R nginx:nginx /var/cache/nginx \
    && chown -R nginx:nginx /etc/nginx/ \
    && chmod -R 755 /etc/nginx/

COPY nginx.conf /etc/nginx/nginx.conf
COPY dist /usr/share/nginx/html      # ← CHANGE THIS

USER nginx
