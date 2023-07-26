FROM node:18.6.0

WORKDIR /var/www/carina-wedding

COPY package*.json ./

RUN npm install

COPY . .

COPY index.html ./

EXPOSE 4000
