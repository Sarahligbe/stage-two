# build stage to build and compile the frontend
FROM node:20-alpine AS build-stage

WORKDIR /frontend

COPY package*.json /frontend/

RUN npm install

COPY ./ /frontend/

RUN npm run build


# compile the app for production with Nginx
FROM nginx:1

COPY --from=build-stage /frontend/dist/ /usr/share/nginx/html

COPY ./nginx.conf /etc/nginx/conf.d/default.conf
COPY ./nginx-backend-not-found.conf /etc/nginx/extra-conf.d/backend-not-found.conf
