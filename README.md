
# How to build image
```
## build docker image
image_name="robinsu/jupyter-selenium:latest"
docker build -t "$image_name" .
```
# Run Container 
### run as deamon 
```
docker run -p 8888:8888 -v $(pwd):/home/jovyan/work "$image_name"

container_name="notebook-01"
image_name="robinsu/jupyter-selenium:latest"
docker run -d --name ${container_name} \
    -v "${PWD}":/home/jovyan/work  \
    -p 8888:8888 \
    -e GRANT_SUDO=yes --user root \
    ${image_name} 
```