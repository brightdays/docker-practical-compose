# Docker Compose Commands
 - compose app using `docker-compose.yml` in current dir
docker-compose up
docker-compose run app1 app2

# Networks in Docker container
- myapp_default network is created
- Default containers are reachable using service
- All services (default on key name - override using --project-name or COMPOSE_PROJECT_NAME) join default_network using its 
- Access to other container using app name defined in yml under services
```yml
services
    server:
    #   ....
    agent1: 
        environment:
        - SERVER_URL=http://server:8111

```
## Resolve network
- Use [link](#links) --link option or connect to some network
- --network="host" localhost:8111 will refer to server container resolve by host

## Links
- @DEPRECATED [Links](https://docs.docker.com/network/links/#communication-across-links) 
 ```
 --link <name or id>:alias
 --link cont1 # same as cont1:cont1
 $ docker inspect -f "{{ .HostConfig.Links }}" web

[/db:/web/db]

 ```

# References
- https://docs.docker.com/compose/compose-file/
- Full docker  : https://medium.com/@mazhar.ansari/dockerised-installation-of-teamcity-server-and-agent-21bcc164af47