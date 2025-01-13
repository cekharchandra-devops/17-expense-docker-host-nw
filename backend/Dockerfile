FROM node:20
EXPOSE 8080
ENV DB_HOST="localhost"
RUN mkdir -p /opt/server
WORKDIR /opt/server
COPY expense-backend/package.json .
COPY expense-backend/*.js .
RUN npm install
CMD ["node", "index.js"]