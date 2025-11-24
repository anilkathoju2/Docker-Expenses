FROM nginx:mainline-alpine3.20-slim

# Install unzip (needed to extract frontend.zip)
RUN apk add --no-cache unzip curl

# Remove default nginx site
RUN rm -rf /usr/share/nginx/html/*

# Download frontend zip
RUN curl -o /tmp/frontend.zip https://expense-joindevops.s3.us-east-1.amazonaws.com/expense-frontend-v2.zip

# Extract frontend content
RUN unzip /tmp/frontend.zip -d /usr/share/nginx/html

# Copy custom nginx config
COPY nginx.conf /etc/nginx/nginx.conf
COPY expense.conf /etc/nginx/conf.d/expense.conf

# Expose port
EXPOSE 80

# Run nginx in foreground
CMD ["nginx", "-g", "daemon off;"]
