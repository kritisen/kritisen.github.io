---
layout: post
published: false
title: Building SciDB plugins using Docker images
---
## Building SciDB plugins

**Aim**: Build and deploy SciDB plugins on a target CentOS system. The target system does not have the libraries required for building 

**Solution**: Grab a SciDB Docker image with the corresponding target OS type, and start a container for that image. Now SciDB docker images typically have the necessary libraries for building plugins. Use the Docker container for building the plugins. 

#### Details

First on target system

```sh
mkdir ~/scratch
cd scratch
git clone https://github.com/paradigm4/<plugin-name>.git # secure_scan in my case

# install docker on target system

# then run a docker image for the target system OS (CentOS 6 here)
docker run -it    \
           --detach   \
           -v ~/scratch:/scratch/ \
           rvernica/scidb:18.1-centos-6 /bin/bash
           
# log into the machine
docker ps # to get the docker container id
docker exec -it <container-id> bash

```

Now within the docker container

```sh
yum install libpqxx-devel # the only dependency that was missing

cd scratch/secure_scan
make
# this creates the required .so file 
```

Back to the target machine

```sh
# copy the plugin to the correct directory
sudo cp ~/scratch/secure_scan/libsecure_scan.so /opt/scidb/18.1/lib/scidb/plugins/
# now the plugin is ready to be loaded 
iquery -aq "load_library('secure_scan')
```