FROM node:20
RUN useradd expense
EXPOSE 8080
WORKDIR /app
COPY . .
RUN npm install
ENV DB_HOST="mysql"
#CMD ["node", "index.js"] 
CMD ["sleep", "20000"]
#RUN dnf install mysql -y
#RUN mysql -h mysql -uroot -pExpenseApp@1 < /app/schema/backend.sql
