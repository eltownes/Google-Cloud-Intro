
## Docker

### init

* `docker login`
* `docker search rocker`
* `docker image ls`
* `docker pull rocker/shiny-verse`
* `docker image rm -f <...>`
* `docker image prune`


### install/run

Notes:
* --rm for dev mode
* -d for detached
* default RStudio Username: rstudio


* `docker run --rm -p 3838:3838 rocker/shiny-verse` 
* `docker container ls`
* `docker run -e PASSWORD=bad_password --rm -p 8787:8787 rocker/tidyverse`
* `docker stop 8df78....`


### volume linking

* `docker run -e PASSWORD=bad_password -d -p 8787:8787 -v /home/ubuntu/analysis:/home/rstudio/volume rocker/tidyverse`
*  `docker container run -e PASSWORD=pw -e USER=katz -p 8787:8787 -v /home/ubuntu/analysis:/home/katz/volume rocker/tidyverse`


### Dockerfile

```
FROM rocker/shiny-verse:latest

RUN apt-get update -qq \
    && apt-get -y --no-install-reommends install \
        lbzip2 \
    && install2.r --error --deps TUE \
        shinywidgets

```

* `docker build . -t shiny-widgets:latest`
* `docker container run -p 3838:3838 shiny-widgets`


To DockerHub
* `docker tag shiny-widgets:latest username/shiny-widgets:latest`
* `docker push username/shiny-widgets:latest`


From DockerHub
* `docker pull username/shiny-widgets:latest`


Misc
* `docker container run -d -p 80:3838 --name srv_test username/shiny-widgets:latest`




