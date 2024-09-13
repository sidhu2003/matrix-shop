FROM node:22-alpine

WORKDIR /app

COPY package*.json ./

COPY . .

RUN npm install

EXPOSE 8000

CMD ["npm", "run", "start"]