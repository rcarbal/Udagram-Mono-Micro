# LOCAL BUILDS
docker run -p 8000:8000 bibleit/udagram-api-feed:local
docker run -p 8001:8001 bibleit/udagram-api-users:local
docker run -p 8080:8080 bibleit/nginx-uda:local
docker run -p 8100:80 bibleit/udagram-frontend:local

# On host network
docker run --network=host bibleit/udagram-api-feed:local
docker run --network=host -v $HOME/.aws:/root/.aws bibleit/udagram-api-feed:local
docker run --network=host bibleit/udagram-api-users:local
docker run --network=host bibleit/nginx-uda:local
docker run --network=host bibleit/udagram-frontend:local
