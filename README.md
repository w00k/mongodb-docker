# mongodb-docker

# By Dockerfile

In the test-mongo-db, you can run it and create a image with Mongo DB, with user/pass test-user/test-password and the database is test-database. 

### Files: 

- Dockerfile this download the docker image and make the user admin for enviroment and create the database admin \  
- mongo-init.js this add the admin user with priviles readWrite on test-database \ 

### For build it, you can do: 

$ docker build -t any_name . 

For see the image: 

$ docker images 

For run it: 

$ docker run -it -p 27017:27017 any_name

# By docker-compose

Create mongo-db enviroment with docker-compose, you have 2 files: \

### Files: 
- docker-compose.yml this download the docker image and make the user admin for enviroment and create the database mydb \  
-  mongo-init.js this add the admin user with priviles readWrite on mydb \ 

### For build it, you can do: 

Download the mongo DB with this cmd:

$ docker-compose up --build -d mongodb 

Run it:

$ docker start mydb

Stop it:

$ docker stop mydb
