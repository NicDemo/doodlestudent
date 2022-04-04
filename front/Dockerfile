 FROM node:14.17.0-alpine as prod_angu
 RUN mkdir -p /app
 WORKDIR /app
 COPY package.json /app
 RUN npm install
 COPY . /app
 RUN npm run build --prod
 FROM nginx:1.20.1
 COPY --from=prod_angu /app/dist/tlcfront /usr/share/nginx/html
 #COPY nginx.conf /etc/nginx/nginx.conf
 EXPOSE 80
