FROM node:9.1.0-alpine

WORKDIR /app

COPY package.json /app/package.json
COPY package-lock.json /app/package-lock.json

RUN npm install --production

COPY . /app

EXPOSE 3000

CMD node index.js
