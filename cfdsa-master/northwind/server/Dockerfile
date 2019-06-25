FROM node:latest

ENV DB_HOST=nwdb \
    DB_PORT=3306 \
    DB_USER=root \
    DB_PASSWORD=changeit \
    APP_PORT=3000 \
    APP_DIR=/app

WORKDIR ${APP_DIR}

ADD main.js .
ADD package.json .

ADD config config
ADD public public
ADD views views

RUN npm install

### run.
EXPOSE ${APP_PORT}

ENTRYPOINT [ "node", "main.js" ]
