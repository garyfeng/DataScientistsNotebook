FROM rocker/rstudio:3.6.2
# see https://hub.docker.com/r/rocker/rstudio/

# add shiny
RUN export ADD=shiny && bash /etc/cont-init.d/add

# Install required libraries
RUN R -e 'install.packages(c("htmltools", "knitr", "rmarkdown"))'

# Install ployly
# the dependency data.table requires zlib.h to be installed
# which in turn needs zlib1g-dev for zlib.
RUN apt-get update && apt-get install -y zlib1g-dev wget curl zip 
RUN R -e 'install.packages(c("plotly"))'

# start RStudio
CMD ["/init"]
