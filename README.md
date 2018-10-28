![Build Status - Master](https://travis-ci.org/raychenon/play-table-of-contents.svg?branch=master)
[![MIT licensed](https://img.shields.io/badge/license-MIT-blue.svg)](https://raw.githubusercontent.com/raychenon/play-table-of-contents/master/LICENSE)

# [Table of Contents](http://tableofcontent.eu)
<!-- Table of contents generated by http://tableofcontent.eu -->
- [Introduction](#introduction)
- [Online Generation](#online-generation)
- [Run locally](#run-locally)
- [Docker](#docker)
  - [Build](#build)
  - [Run locally](#run-locally)
  - [Run on AWS Lightsail](#run-on-aws-lightsail)

# Introduction

[Web based table of contents generator](http://tableofcontent.eu)

There are plenty of markdown table of contents generators on github, but the installation of the dependencies is a lot of overhead for an occasional activity. That's the idea of this web app. 

In addition, it is a nice tutorial on Scala :smile:
 
# Online Generation
You don't need to install anything.
<br>1 Go to http://tableofcontent.eu/
<br>2 Copy paste your markdown content or your github repo link and click "submit"
"

# Run locally

You can run locally, go to the root project and enter this command line. 
```
sbt run
```
By default, it will run on http://localhost:9000 .

To run on local on a specific port
```
sbt "~run 8081"
```

# Docker

## Build

At the root of the project, run the command line and pass in parameter your username on https://hub.docker.com/

```
$ ./build-docker-image.sh <DOCKER_HUB_USERNAME>
```

## Run locally

See the last Docker image build
```
$ docker images
```

To run locally, use the cmd

```
$ docker run --name <CONTAINER_NAME> -p <FROM_PORT>:<TO_PORT> -d <IMAGE_ID>

# for examples :
$ docker run --name container -p 9000:9000 -d e2a451cb675f
```

The application will run on "http://localhost:9000".

To stop every Docker processes from running . 

```
$ docker stop $(docker ps -a -q)
```

Then once the containers stop running, you can delete the containers.
```
$ docker rm $(docker container ps -a -q)
```

## Run on AWS Lightsail

The [instance is already set up](https://github.com/saaste/play-docker-aws-tutorial). Go to the console and run this command:
```
$ sudo docker run --name toc -p 80:9000 -d raychenon/play-table-of-contents:<tag>
```
