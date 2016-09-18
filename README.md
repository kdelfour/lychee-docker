Lychee Dockerfile
=============

This repository contains Dockerfile of Lychee for Docker's automated build published to the public Docker Hub Registry.

# Base Docker Image
[kdelfour/supervisor-docker](https://registry.hub.docker.com/u/kdelfour/supervisor-docker/)

# Installation

## Install Docker.

Download automated build from public Docker Hub Registry: docker pull kdelfour/lychee-docker

(alternatively, you can build an image from Dockerfile: docker build -t="kdelfour/lychee-docker" github.com/kdelfour/lychee-docker)

## Usage

    docker run -it -d -p 80:80 kdelfour/lychee-docker
    
You can add a shared directory as a volume directory with the argument *-v /your-path/uploads/:/uploads/ -v /your-path/data/:/data/ -v /your-path/mysql/:/mysql/* like this :

    docker run -it -d -p 80:80 -v /your-path/uploads/:/uploads/ -v /your-path/data/:/data/ -v /your-path/mysql/:/mysql/ kdelfour/lychee-docker

A mysql server with a database is ready, you can use it with these parameters : 

  - url : localhost
  - database name : lychee
  - user name : lychee
  - user password : lychee
    
## Build and run with custom config directory

Get the latest version from github

    git clone https://github.com/kdelfour/lychee-docker
    cd lychee-docker/

Build it

    sudo docker build --force-rm=true --tag="$USER/lychee-docker:latest" .
    
And run

    sudo docker run -d -p 80:80 -v /your-path/uploads/:/uploads/ -v /your-path/data/:/data/ -v /your-path/mysql/:/mysql/ $USER/lychee-docker:latest
    
Enjoy !!    
