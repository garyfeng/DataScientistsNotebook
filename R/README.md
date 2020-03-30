# RStudio for local testing

We include a custom `Dockerfile` in this folder that installs `shiny server` and `knitr` and other basic libraries. 

The `notebooks` folder is mapped to the RStudio container, where saved notebooks will be persisted. 

Once the docker runs, start your browser to 
- http://localhost:8787/ for RStudio
- http://localhost:3838/ for the shiny server, if something is running

## Dockerfile

The [Dockerfile](Dockerfile) is based on [rocker/rstudio:3.6.2](https://hub.docker.com/r/rocker/rstudio/), the open-source version of RStudio. We custom-installed a number of commonly used libraries, including "htmltools", "knitr", "rmarkdown", "plotly", etc. 

One thing we had to deal with was `data.table`, a dependency of `plotly`, which requires `zlib.h`. It's only available in the dev version of zlib, `zlib1g-dev`. We had to install using `apt-get` before installing the R library.

Installing the R libraries take a long time because we have to compile from the source. This is why it's much faster to load from this custom docker image than from the official one and installing all the libraries every time.


