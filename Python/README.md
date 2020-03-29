# Python notebooks 

In the `docker-compose.yaml` file in the parent folder, we map `./python/notebooks` folder to the docker container as `~/work`, so that notebooks are automatically saved to the host folder. 

We use the `Jupyter Data Science Notebook` version of docker, which contains most of what we need. However, it's missing `pymssql` and `elasticsearch` libraries. Since both are fairly small, we can install them as part of the notebook setup step. 

Alternatively we can create a custom docker image by installing the required libraries. 