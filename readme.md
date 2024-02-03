### Command Docker

Docker run 
```sh
docker run --name [name_container] -v $(pwd)/[path]:[path_container] -p [export]:[inport] -d [images]
```

Mound Volumes connect host directory to container <br/>
'$(pwd)' is root directory
```sh
$(pwd)/[path]:[path_container]
```
<br/>
Docker port mapping [export]:[inport] => host:container
<br/>
### note
Create container and mount file from local connection to a container file <br/>
the container is running in the background process with command -d

====================================================================================
### How to create images and push file to repository

Docker Bulid image
```sh
docker build -t [image_name] ./
```
This command create image from dockerfile in project
```sh
FROM node:alpine
RUN mkdir -p /app
WORKDIR /app
COPY package.json .
COPY . /app
RUN npm install
EXPOSE 3000
CMD ["npm", "run", "dev"]
```

Login Docker for push image to repository Docker Hub
```sh
docker login
```
Push image to repository
```sh
docker push [Image Name]
```
### Update Image container

Docker Commit container to image
```sh
docker commint [id_container] [image_name]
```
Create image from container 

==================================================================================

### how to export images file

```sh
docker save [OPTIONS] IMAGE [IMAGE...]
```

Ex export images file name api-service

```sh
docker save api-service:latest -o api-service.tar 
-- or
docker save --output api-service.tar api-service:latest 
-- or
docker save -o /home/user/api-service.tar api-service:latest 
-- or
docker save -o api-service.tar api-service:latest
```
You will get the file .tar and copy file to server
extract .tar file for use.
```sh
docker load -i api-service.tar 
-- or
docker load -i <path file image>
```

