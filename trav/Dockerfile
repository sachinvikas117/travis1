FROM node:alpine as builder

WORKDIR '/app'

COPY package.json .

RUN npm install

COPY . .

RUN npm run build


FROM niginx

EXPOSE 80

COPY --from=builder /app/build /usr/share/niginx/html


