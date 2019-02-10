FROM node:alpine as build
WORKDIR /app
COPY ./package.json ./
RUN npm install
COPY . . 
RUN npm run start

FROM nginx:alpine
COPY --from=build /app/build /usr/share/nginx/html
COPY ./nginx/default.conf /etc/nginx/conf.d/default.conf
EXPOSE 3000