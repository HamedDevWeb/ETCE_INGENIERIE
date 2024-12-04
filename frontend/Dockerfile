# frontend/Dockerfile
FROM node:14 AS build

WORKDIR /app

COPY package*.json ./

RUN npm install

COPY . .

RUN npx tailwindcss -i ./styles.css -o ./output.css --minify

FROM nginx:alpine

COPY --from=build /app /usr/share/nginx/html
