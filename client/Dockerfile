FROM node:alpine as builder

WORKDIR '/app'

COPY package.json .
RUN npm install

COPY . .

RUN npm run buid

FROM nginx
EXPOSE 3000

COPY --from=builder /app/build /usr/share/nginx/html