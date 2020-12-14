
FROM node:12

WORKDIR /usr/src/app

COPY package*.json ./
RUN npm ci 
# Bundle app source
COPY . .
EXPOSE 8080
CMD [ "npm", "run", "prod" ]