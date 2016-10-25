# companiesHouse_beneficialOwnership
Doodles for working with Companies House Beneficial Ownership Register Data.

This repo creates a set of linked Docker containers to provide a working environment for exploring company data.

The configuration includes:

- a Jupyter notebook server for writing reproducible analysis scripts
- a mongodb container (handy for UK Companies House beneficial ownership JSON data)
- a PostgreSQL container, eg for Companies House company info


I also tried to add in a third party neo4j container seeded with Panama Papers data, but this caused even more memory issues...:-( See the `neo4j_panamapapers` folder.

I assume you have `docker` and `docker-compose` installed.

I needed to up the spec of my docker-machine to run this:

`docker-machine  rm default`
`docker-machine -D create -d virtualbox --virtualbox-disk-size "35000"  --virtualbox-memory 2048 default`

You should now be able to just run:

`docker-compose up -d`

and then launch a Jupyter notebook in your browser.

The notebook is connected to a *mongo* database container. The `Companies House - Significant Control Snapshot - Loader.ipynb` notebook shows how to grab a copy of the UK Companies House beneficial ownership register and load it into the mongo db from a notebook.

 To shutdown the containers:
 
 `docker-compose stop`
 
 and to bring them back up:
 
 `docker-compose start`