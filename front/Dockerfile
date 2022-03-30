FROM node:16.14.2 AS build
WORKDIR /dist/src/app
RUN npm install -g @angular/cli
RUN npm cache clean --force
COPY . .
RUN npm install
RUN ng build --configuration development


FROM nginx:latest AS ngi
COPY --from=build /dist/src/app/dist/express-gaumont /usr/share/nginx/html
COPY /nginx.conf  /etc/nginx/conf.d/default.conf
EXPOSE 80
