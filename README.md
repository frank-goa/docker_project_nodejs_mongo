### docker_project_nodejs_mongo
# Docker Project with nodejs, mongodb and mongo-express

- Docker Tutorials for beginners [Full Course in 3 hours]
- https://www.youtube.com/watch?v=3c-iBn73dDE
- TechWorld with Nana
- Time: 1:10:27

![Blank diagram](https://github.com/frank-goa/docker_project_nodejs_mongo/assets/137857643/6f509d06-f50c-4dcc-9262-fc0ed5d45e0d)


JS, Nodejs application, MongoDB Docker Container 

This demo app shows a simple user profile app set up using
- index.html with pure js and css styles
- nodejs backend with express module
- mongodb for data storage

### Step 1:
Create Docker Network
```bash
docker network create mongo-network 
```
### Step 2:
Start mongodb
```bash
docker run -d -p 27017:27017 -e MONGO_INITDB_ROOT_USERNAME=admin -e MONGO_INITDB_ROOT_PASSWORD=password --name mongodb --net mongo-network mongo
```
### Step 3:
Start mongo-express
```bash
docker run -d -p 8081:8081 -e ME_CONFIG_MONGODB_ADMINUSERNAME=admin -e ME_CONFIG_MONGODB_ADMINPASSWORD=password --net mongo-network --name mongo-express -e ME_CONFIG_MONGODB_SERVER=mongodb mongo-express
```
### Step 4:
Open mongo-express from browser
```bash
http://localhost:8081
```
### Step 5: 
Create user-account db and users collection in mongo-express

### Step 6: 
Start your nodejs application locally - go to app directory of project
