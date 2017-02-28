# Dockerfile for workweek micro-service
Simple RESTful API implementation using MEAN stack deployed by Docker.
## Welcome to Workweek Micro Service Dockerfile ##

**Workweek API** is a simple Micro Service implemented in Express with MongoDB a
s data store.  And easily deployed by Docker in cloud and Linux environment.

### REST API End point ###
- **http://<micro-service-host>/workweek/{wwdate}**




Where **wwdate**  have the format: **yyyy-mm-dd**



## API usage example
Request url:

- curl http://<micro-service-host>/workweek/2015-02-01


Response JSON:

{
  "status": "success", "message" : "", "workweek" : "2015WW06"
}





## Dockerfile.base
Dockerfile.base:

- Dockerfile for building base image locally, use following two lines to build t
he base image, workweek-base


$ mv Dockerfile.base Dockerfile

$ docker build -t workweek-base .

## Dockerfile.mean-stack
Dockerfile.mean-stack:

- Dockerfile for building working image locally, use following two lines to buil
d the work image, workweek-mean-stack


$ mv Dockerfile.mean-stack Dockerfile

$ docker build -t workweek-mean-stack .


## Start micro-service docker image

$ docker run -p 80:80 -d -t workweek-mean-stack


