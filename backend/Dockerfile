FROM node:20
RUN useradd expense
WORKDIR /app
COPY . .
RUN npm install
ENV DB_HOST="mysql"
CMD ['node', 'index.js']
#RUN dnf install mysql -y
#RUN mysql -h mysql -uroot -pExpenseApp@1 < /app/schema/backend.sql
