# DevOpswithDocker-Node.js-Mongodb-Redis-
DevOps with Docker and Node.js + Mongodb/Redis 

Run the Express App 
1. npm init -y (create the package.json)
2. npm install express (to create the express app)
3. Update the index.js file 
4. node index.js ( to start the express app)

Docker commands
1. build image-> docker build -t node-app-image . 
2. list image -> docker images
3. run container with bind mount and env file -> docker run -v D:\Docker\Node-Docker\:/app:ro --env-file ./.env -p 4000:4000 -d --name node-app node-app-image
4. Exec to container -> docker exec -it node-app bash
5. list  containers -> docker ps -a
6. delete container -> docker rm node-app -f
7. delete image -> docker rmi node-app-image 
8. docker compose -> docker-compose up -d 
                  -> docker-compose down -v (-v deletes all unnecessary volume that it creates )
                  -> docker-compse up -d --build (--build will rebuild the image)
                  -> docker-compose -f docker-compose.yml -f docker-compose.dev.yml up -d
9.  sConnect to mondo db container -> docker exec -it devopswithdocker_mongo_1  mongosh -u 'sanjeev' -p 'mypassword'
10. list docker voumes -> docker volume ls 
11. delete unused local volumes -> docker volume prune
11. Create new mondodb -> use mydb
12. list dbs ->  show dbs
13. create a record in mondo db - > db.books.insert({'name':'harry porter'})
14. find the record -> db.books.find()
15. use monogodb for the express app -> npm install mongoose
16. docker networking -> bridge and host are default network
                      -> docker network ls
                      -> docker inspect name_of_container
                      -> docker network inspect devopswithdocker_default (name of the custom network)
17. docker compose build  -> docker-compose -f docker-compose.yml -f docker-compose.dev.yml up -d --build -V
18. docker compose scale -> docker-compose -f docker-compose.yml -f docker-compose.dev.yml up -d --scale node-app=2
19. docker compose build for specific app -> docker-compose -f docker-compose.yml -f docker-compose.dev.yml up -d --build --no-deps node-app
20. docker compose force recreate container -> docker-compose -f docker-compose.yml -f docker-compose.dev.yml up -d --build --force-recreate --no-deps node-app
21. Rename the docker image --> docker image tag node-app smishra04/node-app   
22. Push the image to docker hub --> docker push smishra04/node-app:latest 
