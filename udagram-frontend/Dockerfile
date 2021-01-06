## Build
## docker build -t udagram-frontend .
FROM beevelop/ionic AS ionic
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

# Create app directory
WORKDIR /usr/src/app
# Install app dependencies
# A wildcard is used to ensure both package.json AND package-lock.json are copied
# where available (npm@5+)
COPY package*.json ./
RUN npm ci
# Bundle app source
COPY . .
# RUN ionic init

RUN ionic build   
## Run
FROM nginx:alpine
#COPY www /usr/share/nginx/html
COPY --from=ionic  /usr/src/app/www /usr/share/nginx/html

# docker build ./udagram-frontend -t udagram-frontend -f udagram-frontend/Dockerfile