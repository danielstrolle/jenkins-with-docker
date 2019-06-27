# jenkins-with-docker
Dockerized base Jenkins image.

## Usage
`sudo docker run --name jenkins-with-docker -p 8080:8080 -p 50000:50000 -v /var/run/docker.sock:/var/run/docker.sock danielstrolle/jenkins-with-docker:lts`

Similar to the base Jenkins image run, also exposes the host machines Docker socket to the Container, allowing Docker commands to be ran.

## Update/Maintenence
To update the image on docker hub:
  - login to docker hub with `sudo docker login`
  - rebuild the image locally `sudo docker build -t "jenkins-with-docker" .` 
      - the -t arguement tags the image as jenkins-with-docker
      - the . gives it the context when building
  - run `sudo docker images` to get see the image you created.
  - run `sudo docker tag {REPLACE_WITH_IMAGE_ID} danielstrolle/jenkins-with-docker:lts` to tag your image.
  - push to docker hub with `sudo docker push danielstrolle/jenkins-with-docker:lts`
  - You should see something like "The push refers to repository [docker.io/danielstrolle/jenkins-with-docker]"
  - After this command is completed successfully, it has been successfully updated.
