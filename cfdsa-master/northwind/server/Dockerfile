FROM node:latest

ENV DB_HOST=northwind_db  DB_PORT=3306 DB_USER=root DB_PASSWORD=changeit \
  APP_PORT=5000 APP_DIR=/northwind

WORKDIR ${APP_DIR}

ADD config config
ADD public public
ADD views views
ADD main.js .
ADD package.json .

RUN npm install

EXPOSE ${APP_PORT}

ENTRYPOINT [ "node", "main.js" ]