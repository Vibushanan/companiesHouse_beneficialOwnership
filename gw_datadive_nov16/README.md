# Notes from Global Witness / DataKind Datadive, November 2016

Various notes and fragments...

# Datakind / Global Witness Datadive

To get these scripts up and running, you will need to install Docker on your computer or be able to run Docker containers on a third party cloud server. 


*Note - there seemed to be a problem running newly downloaded versions of docker on Macs:-(*

## Mac 10.10.3 and up /  Windows 10 :
[Download and install Docker](https://docs.docker.com/engine/getstarted/step_one/)
Launch Docker.
From the Docker menu, download and install Kitematic.

## Old Mac:

Download and install the [Docker Toolbox](https://www.docker.com/products/docker-toolbox).

## All
Download the contents of this repository and ensure they're in a directory you can find.

Launch Kitematic.

From the bottom right hand corner of Kitematic you can open a Docker command line (Docker CLI).

On the Docker command line, change directory to the directory containing the `docker-compose.yml` file and run the command:

`docker-compose up -d`

This will launch a database container linked to a Jupyter notebook server.

To stop the containers: `docker-compose stop`
To start the containers back up again: `docker-compose start`

To destroy the containers and their contents: `docker-compose down`
