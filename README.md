# mental-health-docker
The docker files for mental-health projects.
**There are two paths for startup here**
#####1
Start nginx, web service, data service, and business service respectively. At this point the business process will run in a container. (Since they are started separately, it is convenient to manage and control the startup order independently)
Use the following code in sequence:
```
docker-compose -f docker-compose-nginx.yml up -d
docker-compose -f docker-compose-data.yml up -d
docker-compose -f docker-compose-server.yml up -d
docker-compose -f docker-compose-web.yml up -d
```
#####2
Start nginx separately and start the other services at once. At this point, the business processes will run in separate containers.
Use the following code:
```
docker-compose -f docker-compose-nginx.yml up -d
docker-compose -f docker-compose.yml up -d
```
