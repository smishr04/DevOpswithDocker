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
