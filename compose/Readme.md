Create mongo-db enviroment on docker

version: '3.7'

services:
    mongodb:
        image: mongo:latest
        container_name: mongodb
        restart: always
        environment:
            MONGO_INITDB_ROOT_USERNAME: <admin-user>
            MONGO_INITDB_ROOT_PASSWORD: <admin-password>
            MONGO_INITDB_DATABASE: <database to create>
        ports:
            - 27017:27017
        volumes:
            - ./mongo-init.js:/docker-entrypoint-initdb.d/mongo-init.js:ro

Create the user for database, insctructions on mongo-init.js 

db.createUser(
        {
            user: "<user for database which shall be created>",
            pwd: "<password of user>",
            roles: [
                {
                    role: "readWrite",
                    db: "<database to create>"
                }
            ]
        }
);


Start the mongo DB with this cmd

$ docker-compose up --build -d mongodb 
