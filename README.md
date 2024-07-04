Download Docker desktop client <br>
https://www.docker.com/products/docker-desktop/<br>
Get started<br>
Clone a sample git repository using the below command or use your project for the demo:<br>
git clone https://github.com/docker/getting-started-app.git<br>
cd into the directory<br>
cd getting-started-app/<br>
Create an empty file with the name Dockerfile<br>
touch Dockerfile<br>
Using the text editor of your choice, paste the below content ( Details about each of these have already shared in the video)<br><br>
FROM node:18-alpine<br>
WORKDIR /app<br>
COPY . .<br>
RUN yarn install --production<br>
CMD ["node", "src/index.js"]<br>
EXPOSE 3000<br><br>
Build the docker image using the application code and Dockerfile<br>
docker build -t day02-todo .<br>
Verify the image has been created and stored locally using the below command:<br>
docker images<br>
Create a public repository on hub.docker.com and push the image to remote repo<br>
docker login<br>
docker tag day02-todo:latest username/new-reponame:tagname<br>
docker images<br>
docker push username/new-reponame:tagname<br>
To pull the image to another environment , you can use below command<br>
docker pull username/new-reponame:tagname<br>
To start the docker container, use below command<br>
docker run -dp 3000:3000 username/new-reponame:tagname<br>
Verify your app. If you have followed the above steps correctly, your app should be listening on localhost:3000<br>
To enter(exec) into the container, use the below command<br>
docker exec -it containername sh
or
docker exec -it containerid sh
To view docker logs
docker logs containername
or
docker logs containerid
