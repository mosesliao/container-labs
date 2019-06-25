FROM node:latest

# Define my environment variables
ENV APP_PORT=5000 APP_DIR=/fortune

# create WORKDIR, and change directory to it
WORKDIR ${APP_DIR}

# Copy files to WORKDIR
ADD main.js .
ADD package.json .
# directory must have a target name
ADD public public
ADD views views

EXPOSE ${APP_PORT}

HEALTHCHECK --interval=60s --timeout=5s --start-period=5s --retries=3 \
  CMD curl -f -s http://localhost:${APP_PORT}/health || exit 1

# install libraries from package.json
RUN npm install

# how should the image be executed
ENTRYPOINT [ "node", "main.js" ]

# CMD [ "3000" ]
