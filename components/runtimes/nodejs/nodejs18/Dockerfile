# image base on node:18.20.1-alpine3.19
FROM node@sha256:6d9d5269cbe4088803e9ef81da62ac481c063b60cadbe8e628bfcbb12296d901

ARG NODE_ENV
ENV NODE_ENV $NODE_ENV
ENV npm_config_cache /tmp/

RUN mkdir -p /usr/src/app
RUN mkdir -p /usr/src/app/lib
WORKDIR /usr/src/app

COPY ./nodejs18/package.json /usr/src/app/
RUN npm install && npm cache clean --force
COPY ./lib /usr/src/app/lib

COPY ./server.js /usr/src/app/server.js

CMD ["npm", "start"]

EXPOSE 8888
