#IMAGEN OFICIAL NGINX
FROM nginx
#COPIAR EL ARCHIVO INDEX.HTML AL DIRECTORIO /usr/share/nginx/html
COPY index.html /usr/share/nginx/html
export DOCKER_BUILDKIT=0
export COMPOSE_DOCKER_CLI_BUILD=0
docker build -t my-image .

#ENPONER EL PUERTO 80 
#EXPOSE 80
