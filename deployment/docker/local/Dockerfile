# docker build ./deployment/docker/local -t nginx-uda -f deployment/docker/local/Dockerfile
# docker run -p 8080:8080 bibleit/nginx-uda:local
FROM nginx:alpine

COPY nginx-uda.conf /etc/nginx/nginx.conf