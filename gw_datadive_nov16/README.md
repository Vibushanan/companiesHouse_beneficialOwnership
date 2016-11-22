# Notes from Global Witness / DataKind Datadive, November 2016

Various notes and fragments...

# Datakind / Global Witness Datadive

To get these scripts up and running, you will need to install Docker on your computer or be able to run Docker containers on a third party cloud server. 


Note - there seems to be a problem running newly downloaded versions of docker on Macs:-(


The following `docker-compose.yml` file contents will download and install 

#----------------- START docker-compose.yml ------------------
#mongodata:
#    image: busybox
#    volumes: 
#        - /data/db

#mongodb:
#    image: mongo
#    ports:
#        - "27107:27107"
#    volumes_from:
#        - mongodata
#    command: --smallfiles
    
postgresdatadd:
    image: busybox
    volumes: 
        - /var/lib/postgresql/data

postgresdd:
    image: postgres #mdillon/postgis 
    environment:
        - POSTGRES_PASSWORD=PGPass
    ports:
        - "5432:5432"
    volumes_from:
        - postgresdatadd
        

neo4jch:
  image: neo4j
  ports:
    - "7474:7474"
    - "1337:1337"
  volumes:
    - /opt/data

    
datadive:
    image: jupyter/scipy-notebook
    user: root
    environment:
        - GRANT_SUDO=yes
    ports:
        - "9988:8888"
    links:
        #- mongodb:mongodb
        - postgresdd:postgres
        - neo4j:neo4j
    volumes:
        - .:/home/jovyan/work

#----------------- END docker-compose.yml ------------------

Download and install Kitematic. From the bottom right hand corner of Kitematic you can open a Docker command line. Change directory to the directory containing the `docker-compose.yml` file and run the command:

`docker-compose up -d`

This will launch a database container linked to a Jupyter notebook server.

To stop the containers: `docker-compose stop`
To start the containers back up again: `docker-compose start`

To destroy the containers and their contents: `docker-compose down`
