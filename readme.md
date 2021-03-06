
Starting point for a Docker Web Server
======================================

Nginx proxy containers
----------------------
This container provides virtual host routing of requests on port 80 to nginx containers registered with their host name.


Logspout which logs to papertrail
---------------------------------
This container forwards all log output on stdout and stderr to papertrail.

Development machine setup
-------------------------

For development on OSX and Windows I recommend you install Kinematic: https://kitematic.com/

Once Kitematic is installed then 'Install Docker Commands' from the Kitematic menu. This installs the docker command line utilities.


Production Server Setup
-----------------------
1. Install Docker
   https://docs.docker.com/installation/

2. Install Docker Compose:
   https://docs.docker.com/compose/install/

3. Clone the Docker Web Server
   ```
   git clone https://github.com/dylangmiles/docker-webserver.git docker-webserver
   ```
4. Replace vars in your docker compose file
   ```
   ./docker-compose-replacevars.sh docker-compose-prod.yml docker-compose.yml HOSTNAME=servername
   ```

Start the services
------------------
```
docker-compose up -d proxy
```

```
docker-compose up -d logspout
```

Once you start your other services you should be able to browse to them with with their domain name on port 80!
