FROM node:latest
# FROM node@sha256:b074182f4154dd72be42912e908674a5b00a85b98a1dfad497f44e366076c790
# docker inspect node -> Id

ENV APP_PORT=5000 APP_DIR=/fortune

# create (if not exit) and cd to
WORKDIR ${APP_DIR}

# For directory, the destination must give a name
ADD main.js .
ADD package.json .
ADD public public
ADD views views

# install libraries from package.json
RUN npm install

## Docker run
# useless - for documentation
EXPOSE ${APP_PORT}

HEALTHCHECK --interval=60s --timeout=5s --start-period=5s --retries=3 \
    CMD curl -f -s http://localhost:${APP_PORT}/health1 || exit 1

# how the image should be executed
ENTRYPOINT [ "node", "main.js" ]

# Options
# CMD ["3000"]