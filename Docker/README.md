# Docker

We use `Docker` and `docker-compose` to set up portable and repeatable environments for the exercises. 

Install docker on your machine (called the "host machine") from http://www.docker.com. 

You should also get a login at http://www.dockerhub.com, which is needed to use docker.

For this exercise we will launch a bunch of docker containers, including
- a Microsoft SQL Server (`mssql`)
- a Jupyter notebook with data science libraries preinstalled (`jupyter`)
- a RStudio v3.6.1 (`rstudio`) with the RStudio interface and the `shiny server`.
- an Elasticsearch server (`elasticsearch`)
- a Kibana server for data visualization

It is recommended that you give adequate resources to docker. Launch `docker` on your host machine, and in settings or preferences, adjust the CPU, memory, and hard drive space.

