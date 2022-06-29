FROM node:16

WORKDIR /usr/src/app

COPY files/package*.json ./

RUN npm install

COPY ./files/* .

EXPOSE 8080
CMD [ "node", "server.js" ]