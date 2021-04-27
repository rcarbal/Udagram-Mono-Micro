# docker run -p 8080:8080 bibleit/udagram-api-users
# docker run -p 8001:8001 bibleit/udagram-api-users:local
FROM node:12

# uncomment below if you will set the envs through the command line docker build

ARG POSTGRES_USERNAME
ARG POSTGRES_PASSWORD
ARG POSTGRES_HOST
ARG POSTGRES_DB
ARG AWS_BUCKET
ARG AWS_REGION
ARG AWS_PROFILE
ARG JWT_SECRET
ARG URL

ENV POSTGRES_USERNAME=$POSTGRES_USERNAME \ 
    POSTGRES_PASSWORD=$POSTGRES_PASSWORD \
    POSTGRES_HOST=$POSTGRES_HOST \
    POSTGRES_DB=$POSTGRES_DB \
    AWS_BUCKET=$AWS_BUCKET \
    AWS_REGION=$AWS_REGION \
    AWS_PROFILE=$AWS_PROFILE \
    JWT_SECRET=$JWT_SECRET \
    URL=$URL

WORKDIR /usr/src/app

COPY package*.json ./
RUN npm ci 
# Bundle app source
COPY . .
EXPOSE 8080
CMD [ "npm", "run", "prod" ]