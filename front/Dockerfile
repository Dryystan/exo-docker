FROM node:latest
WORKDIR /usr/app
COPY package*.json .
COPY . ./

FROM nginx
COPY docker/nginx/default.conf /etc/nginx/conf.d/default.conf
COPY --from=compile-image /opt/ng/dist/app-name /usr/share/nginx/html
