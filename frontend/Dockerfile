FROM nginx
RUN rm -rf /usr/share/nginx/html/*
RUN rm -rf /etc/nginx/default.d/expense.conf
RUN rm -rf /etc/nginx/conf.d/default.conf
COPY expense.conf /etc/nginx/default.d/expense.conf
COPY static /usr/share/nginx/html/
