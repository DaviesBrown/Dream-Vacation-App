FROM node:20-alpine AS build

WORKDIR /app

COPY package.json package-lock.json ./

RUN npm install -g serve

RUN npm ci --only=production

COPY . .

ENV NODE_OPTIONS=--openssl-legacy-provider

RUN npm run build

CMD [ "serve", "-s", "build" ]
