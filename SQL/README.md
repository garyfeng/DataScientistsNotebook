# Play with SQL

Creating an environment to practice SQL 

----

## Microsoft SQL Server 2019

We will build a custom SQL Server docker image using the [official Microsfot SQL Server 2019 docker image](https://hub.docker.com/_/microsoft-mssql-server) as the base, and add data and configuration to make it work with the rest of the elements.

The original plan was to -- in `entrypoint.sh` -- start the mssql server and then the `import-data.sh` script to create a database/data table in the SQL Server. This can work, but after `import-data.sh` the docker just quits. I was able to stop that with a trick involving using `tail -F anything` which creates an error. The docker container does not quit anymore, but nor does it respond to incoming queries.

So I had basically removed the `import-data.sh` step for now, starting the sql server empty. 

We will use python/SQL to insert data. 

Also, the data is not persistent for now, by design. 

## MySQL 

We will build a custom SQL Server docker image using the [official MySQL 5.7 docker image](https://hub.docker.com/_/mysql?tab=tags) as the base, and add data and configuration to make it work with the rest of the elements.

