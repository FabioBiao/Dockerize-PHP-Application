# Youtube
Tutorial source code.


- https://www.youtube.com/watch?v=1zWFxri51qQ

# Exlanation of docker file
- grabs php image from docker
- update linux instance with apt-get and update
- install php modules
- add our app into apache web server directory
- copy configuration file (my-site.conf)
- set environment variables (line 6-11)
- expose port 80

# docker-compose.yml
Run containers locally
- webserver (we can name this whatever we want, is what we are going to call our app moving fwd)
- image name, same as above
- ports 
1. left side, we can set any port (usefull 80 for localhost)
2. right side, where it hits the webserver service
- Volumes, we can comment if we run from docker
1. go to the app direcotry
- environment, defines environment variables
- networks 
    1. usefull if we want to run a local sequel db instance for example, and then we define the network as external


# running it
1. ensure docker desktop is running 
- comment volumes (if wyou want to point to the docker image itself)
2. docker build -t mydemophpimage .
- mydemophpimage, image name we gave it
- . - defines local directory
3. check if img was created
- docker image ls | grep mydemophpimage  (linux)
- docker image ls | findstr mydemophpimage (windows)
4. run the image
- docker-compose up
- docker-compose up -d
- docker compose up --watch  (preview changes on the fly)
5. access via browser
- http://localhost/

6. go into our image
- docker ps | findstr mydemophpimage (windows)  
On new terminal, so that we can get the container name (dockerize-php-application-webserver-1 is the name in this case)
- docker exec -it dockerize-php-application-webserver-1 bash
