FROM node:22-alpine3.19 as builder

WORKDIR /app

ENV NODE_OPTIONS=--openssl-legacy-provider
ENV REACT_APP_API_URL=http://localhost:8000

COPY package.json /app

RUN npm install

COPY . /app

RUN npm run build

FROM nginx:latest

COPY --from=builder /app/build /usr/share/nginx/html

EXPOSE 80