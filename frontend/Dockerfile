FROM node:11.10.0 as base
WORKDIR /tmp
COPY . .
RUN npm install && npm run build --prod

FROM nginx:1.15.8
COPY ./nginx.conf /etc/nginx/nginx.conf
COPY --from=base /tmp/dist/top-movies-frontend /var/www
