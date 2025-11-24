FROM nginx:mainline-alpine3.20-slim

# Remove default nginx files
RUN rm -rf /usr/share/nginx/html/*

# Copy ONLY frontend build files
COPY index.html /usr/share/nginx/html/
COPY asset-manifest.json /usr/share/nginx/html/
COPY robots.txt /usr/share/nginx/html/
COPY static /usr/share/nginx/html/static

# Add reverse proxy config
RUN mkdir -p /etc/nginx/conf.d

RUN printf "server {\n\
    listen 80;\n\
    server_name _;\n\
    root /usr/share/nginx/html;\n\
\n\
    location / {\n\
        try_files \$uri \$uri/ /index.html;\n\
    }\n\
}\n\
\n\
server {\n\
    listen 80;\n\
    server_name _;\n\
\n\
    location /api/ {\n\
        proxy_pass http://backend:8080/;\n\
        proxy_http_version 1.1;\n\
    }\n\
\n\
    location /health {\n\
        stub_status on;\n\
        access_log off;\n\
    }\n\
}\n" > /etc/nginx/conf.d/expense.conf

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]
