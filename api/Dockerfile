# Image's instructions

# the first layer(the parent image): pull in the node image
FROM node:17-alpine

# installs nodemone package globally in the image 
RUN npm install -g nodemon

# run all the future instructions form the '/app' directory
WORKDIR /app

# copy the package.json into the image
COPY package.json .

# installs all the dependencies listed in th package.json file
RUN npm install

# copy our source code into the image(from the curr dir to the curr dir) 
COPY . .


# Container's instructions(will run when the container begins to run)

# what port is gonna be exposed by the container(optional: need only when use the docker desktop application)
EXPOSE 4000

# run the 'dev' script from the package.json file, inside the container
CMD ["npm", "run", "dev"]


# Docker commands:
# building an image: docker build -t 'app name':'version' .
# shows the images details: docker images
# runs an image to create a container(need image's ID/name): docker run --name 'container name' -p 'port':'port' -d --rm -v 'path':'/app' -v /app/node_modules 'app name':'version'
# note: the '-p' flag means publish, maps the container's port to a port on our computer to the host computer
# note2: the '-d' flag means ditached, the terminal detached from the proces
# note3: the '--rm' flag means remove, remove the container once we stop it later on
# note4: the -v flag means volume, maps our project folder on our computer to the app foler in the container 
# note5: the second -v flag, maps our node_modules to a folder managed by docker somewhere on our computer
# shows a list of running containers: docker ps
# note: we can add '-a' at the end to show all the docker(including those which are not running)
# stopping the container: docker stop 'container name'
# restart a container: docker start 'container name'
# note: adding '-i' after the word start, will show us the console logs
# delete an image: docker image rm 'image name'
# note: adding '-f' at the end will force to delete the image 
# delete a container: docker container rm 'container name'
# note: it's possible to remove more than one container in one command
# removing all the containers, all images and all volumes: docker system prune -a 

# Compose

# run the images and start up a containers: docker-cmopose up
# stop and delete the containers: docker-compose down --rmi all -v
# note1: the -rmi flag means remove image
# note2: the 'all' means remove all the images
# note3: means removes remove the volumes

# Docker Hub

# run an image from Docker Hub: docker bulid -t 'user name/image name' .
# log in: docker login 
# push up to the repository: docker push 'user name/image name'
# pull an image from a repository: docker pull 'user name/image name'
