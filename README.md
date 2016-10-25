# companiesHouse_beneficialOwnership
Doodles for working with Companies House Beneficial Ownership Register Data


If you have `docker` and `docker-compose` installed, should be able ti just run:

`docker-compose up -d`

and then launch a Jupyter notebook in your browser.

The notebook is connected to a *mongo* database container. The `Companies House - Significant Control Snapshot - Loader.ipynb` notebook shows how to grab a copy of the UK Companies House beneficial ownership register and load it into the mongo db from a notebook.

 To shutdown the containers:
 
 `docker-compose stop`
 
 and to bring them back up:
 
 `docker-compose start`