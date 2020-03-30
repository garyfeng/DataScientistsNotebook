# Python notebooks 

In the `docker-compose.yaml` file in the parent folder, we map `./python/notebooks` folder to the docker container as `~/work`, so that notebooks are automatically saved to the host folder. 

We use the `Jupyter Data Science Notebook` version of docker, which contains most of what we need. However, it's missing `pymssql` and `elasticsearch` libraries. Since both are fairly small, we can install them as part of the notebook setup step. 

Alternatively we can create a custom docker image by installing the required libraries. 

## Security

I have removed the password protection for the Jupyter Notebook server. See https://stackoverflow.com/questions/41159797/how-to-disable-password-request-for-a-jupyter-notebook-session

This makes it easy for local testing with `docker-compose`, but it is a security risk. For deployment, one must reinstate the password protection as well as the SSL Certification.
