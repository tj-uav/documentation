---
description: Instructions to install the AUVSI interop server library on a raspberry pi
---

# Interop Server

### About

The interop server is how we can receive the competition details \(where the waypoints are, where the obstacles are, etc.\) and submit our telemetry and ODCL data. For testing purposes, the interop server will be setup on a raspberry pi that we can communicate to over WiFi.

### Setup

Install docker and docker-compose: 

```text
sudo apt-get update && sudo apt-get upgrade
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh get-docker.sh

# Test docker
sudo docker version
sudo docker info
sudo docker run hello-world

sudo pip3 -v install docker-compose
```

Clone the interop repo at [https://github.com/auvsi-suas/interop.git](https://github.com/auvsi-suas/interop.git) and navigate to /interop/server

Since the interop source was written for a different architecture and OS, we need to change some build files. The edits for the two attached files are explained in the **Edits** section. Rename Dockerfile.txt to Dockerfile. Copy requirements.txt into /config

{% file src="../../../.gitbook/assets/dockerfile.txt" %}

{% file src="../../../.gitbook/assets/interop-server.sh" %}

{% file src="../../../.gitbook/assets/requirements.txt" %}

```text
sudo ./interop-server.sh create_db
sudo ./interop-server.sh load_test_data
sudo ./interop-server.sh up
```

### Edits

**Dockerfile**

Since we're configuring this on a Raspberry Pi, we need to specify the computer's architecture is ARMv7 instead of x86. In the first line of interop/server/Dockerfile, change _FROM ubuntu:20.04_ to _FROM armv7/armhf-ubuntu:latest_

Some later packages need updated apt repositories \(package lists\). After each list update, apt-get needs to refresh.

_RUN apt-get -qq update && apt-get install software-properties-common -y && add-apt-repository ppa:deadsnakes/ppa && apt-get -qq update && apt-get -qq install -y_

The packages \[_libjpeg-dev  zlib1g-dev_ \] must be installed to later build  Pillow in python3.6

The package _libpq-dev_ is necessary to build psycopg2 later. 

_Python3.6_ and _python3.6-dev_ need to be explicitly installed as Ubuntu 16:04 defaults to python 3.5.

_Cython_ must be pip installed before requirements.txt is pip installed, because it needs to be completely built to set up some of the wheels in requirements.txt packages \(django, matplotlib\). 

For some reason, django can't find its nodejs environment in our container. To fix this, run ln -s /usr/bin/nodejs /usr/bin/node

Lastly, all instances of ./&lt;python-file&gt; or python3 &lt;python-file&gt; were replaced with python3.6 &lt;python-file&gt; as python 3.5 is default on ubuntu 16:04. 

**requirements.txt:**

The armhf container has some trouble building psycopg2 \(a python library that communicates with a PostgreSQL database\), so we need to install its binaries. \[Change psycopg2 -&gt; psycopg2-binary\]

Pyproj only works on this image under version 1.9.6. \[Change pyproj -&gt; pyproj==1.9.6\]

### Usage

how to make missions  
stuff u can do as admin  
how to view telemetry data that gets submitted  
how to view odcl data that gets submitted

### Debugging

To get a list of images, containers, and their IDs

`sudo docker image ls`

`sudo docker container ls`

To start a terminal inside a docker image:

`sudo docker run -it <image id> bash`

To remove all images:

`sudo docker rmi -f $(sudo docker images -a -q)`

To remove all unused images \(safer\):

`sudo docker system prune`

If strange errors arise in interop setup, try reverting to armv7/armhf-ubuntu:16.04 to use the older xenial release.

