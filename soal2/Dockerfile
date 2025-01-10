FROM node:20.18-alpine AS builder

WORKDIR /app

COPY package.json .

RUN npm install

COPY . .

RUN npm run build

FROM nginx:alpine 

WORKDIR /app

COPY nginx/default.conf /etc/nginx/conf.d/

COPY --from=builder /app/dist ./

EXPOSE 80