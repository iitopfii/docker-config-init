### Command Docker

Docker Mount Volumes
```sh
docker run --name [name_container] -v $(pwd)/[path]:[path_container] -p [export]:[inport] -d [images]
```
Create container and mount file from local connection to a container file <br/>
the container is running in the background process with command -d


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
