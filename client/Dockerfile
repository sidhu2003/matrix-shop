FROM node:22-alpine3.19 as builder

WORKDIR /app

ENV NODE_OPTIONS=--openssl-legacy-provider

COPY package.json /app

RUN npm install

COPY . /app

RUN npm run build

FROM nginx:latest

COPY --from=builder /app/build /usr/share/nginx/html

EXPOSE 80