FROM node as builder

EXPOSE 80

WORKDIR /usr/app

COPY ./package.json ./
RUN npm install

COPY . .

RUN npm run build

FROM nginx:1.11

COPY --from=builder /usr/app/dist /usr/share/nginx/html
