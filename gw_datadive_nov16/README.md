# Notes from Global Witness / DataKind Datadive, November 2016

Various notes and fragments...

# Datakind / Global Witness Datadive

To get these scripts up and running, you will need to install Docker on your computer or be able to run Docker containers on a third party cloud server. 


*Note - there seemed to be a problem running newly downloaded versions of docker on Macs:-(*

Download and install Kitematic. From the bottom right hand corner of Kitematic you can open a Docker command line.

Download the contents of this repository and ensure they're in a directory you can find.

Change directory to the directory containing the `docker-compose.yml` file and run the command:

`docker-compose up -d`

This will launch a database container linked to a Jupyter notebook server.

To stop the containers: `docker-compose stop`
To start the containers back up again: `docker-compose start`

To destroy the containers and their contents: `docker-compose down`
