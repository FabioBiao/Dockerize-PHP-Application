# Youtube
https://www.youtube.com/watch?v=ZX6ENJruhzI&list=PLQH1-k79HB396mS8xRQ5gih5iqkQw-4aV&index=4

https://github.com/GaryClarke/docker-php/tree/main

# setting up nginx
- docker ps  - list running containers
- docker exec -it morecomplex-web-1 sh   
cat /etc/nginx/conf.d/default.conf - to look at nginx configuration

- docker compose up -d  (detach mode so we get the terminal back)

- docker compose -f docker-compose.dev.yaml up --env-file 

# php
alpine minial configuration


docker build -t mytest:php81 -f php/Dockerfile .
- t set a name "mytest"
- f sets the path to the docker file folder
- . from the current location
- docker exec -it morecomplex-app-1 sh    | go inside container

- docker compose down

run dev composer
- docker compose -f docker-compose.dev.yaml up --build -d
# run docker compose dev
- docker compose 

# composer
install dependencies
- composer install --ignore-platform-reqs
- composer dump-autoload | so that autoload will work

# runninng specific env
- docker compose -f docker-compose.dev.yaml --env-file .env.local up --build -d

# debugging PHP with php storm
https://www.youtube.com/watch?v=sSSL8t4LBac&list=PLQH1-k79HB396mS8xRQ5gih5iqkQw-4aV&index=12


# pushing to container registry
- docker login -u username
- docker build --target app -t garyclarky/php-composer:1.0 -f ./php/dockerfile .
- docker push garyclarky/php-composer:1.0


# test
- we added tests folder and phpunit.xml
- we run the tests via github actions
