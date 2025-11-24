FROM nginx:mainline-alpine3.20-slim

# Remove default nginx webpage
RUN rm -rf /usr/share/nginx/html/*

# Copy your static frontend files
COPY . /usr/share/nginx/html

# Global nginx configuration (you can keep default)
# If you have a custom nginx.conf, copy it here:
# COPY nginx.conf /etc/nginx/nginx.conf

# Create reverse proxy configuration
RUN mkdir -p /etc/nginx/conf.d

RUN printf "server {\n\
    listen 80;\n\
    server_name _;\n\
\n\
    proxy_http_version 1.1;\n\
\n\
    root /usr/share/nginx/html;\n\
\n\
    location /api/ {\n\
        proxy_pass http://backend:8080/;\n\
    }\n\
\n\
    location /health {\n\
        stub_status on;\n\
        access_log off;\n\
    }\n\
\n\
    location / {\n\
        try_files \$uri \$uri/ /index.html;\n\
    }\n\
}\n" > /etc/nginx/conf.d/expense.conf


EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]
