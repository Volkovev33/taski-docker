FROM node:16-alpine as builder
WORKDIR /app

COPY package.json package.json
COPY package-lock.json package-lock.json

RUN npx update-browserslist-db@latest
RUN NODE_ENV=development npm i
COPY . .
RUN npm run build

CMD ["npx", "-y", "http-server", "-p", "8000", "/app/build"]
