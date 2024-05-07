# 1 THE CHOICE OF BASE IMAGE.

The choice base image is the Node.js alpine image since they are suitable for resource-constrained environments or when minimizing image sizes is a priority of which in this case is a requirement.

# 2 THE DOCKERFILE DIRECTIVE.

Dockerfile directive is that  the base images is node:14-alpine,which the create a working directory to in the path client/app and backend/app ,afterwards the images copy the dependencies from the package.json file run npm install to install any other required dependencies for running the image .The image then copies the files in the root of the project .In backend the port 5000 is exposed for viewing results as well as in client the port 3000 is exposed and the results can be viewed from there.
Lastly the CMD commands are run once the image is run.

# 3 DOCKER-COMPOSE NETWORKING.

Since the containers created need to be communicating a network is created for which mine is yolo_net which enable the containers to communicate once lauched .
I also applied the ports for viewing of the results.

# 4 DOCKER-COMPOSE VOLUME

Docker volumes that I created enable the data of the containers to be stored outside the container that way to enable persistence even when the container are not running.
For the client-container1 the data is to be stored ("./client:/var/www/client") in this directory while for the backend ("./backend:/var/www/backend") and finally for the yolo.db (mongo-data:/data/db) in this directory.

# 5 GIT WORKFLOW USED FOR ACHIEVEMENT.

Firstly I followed the instruction as illustrated on the readme file.
I then changed directory to the client where I created a dockerfile for  creating the image.I run the docker build command to create the image and finally docker run command to create and run the container to check whether the conatiner was running correctly. I followed the same steps in the backend directory and with the conatiners running smoothly as shown in the exposed ports I deleted the images created and conatainers and configured the docker-compose file in the root directory to reacte them and also run docker-compose push to show the images in the dockerhub as evident from the screenshot attached.

# 6 SCREENSHOT OF SUCCESSFUL TAGGING THE IMAGE AND PUSHING IT TO DOCKERHUB.

Below is a screenshot of the images build when i run docker-compose build and docker-compose push.
![alt text](<Screenshot from 2024-04-30 22-34-14-1.png>)