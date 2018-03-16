---
layout: post
published: false
title: Improving the workflow for deploying SciDB libraries
subtitle: >-
  Leveraging Docker to build SciDB libraries, and Github gh-pages to host
  binaries
---
Run SciDB 18.1 CE with shim and plugins

```sh
docker run -it 
           --detach 
           -p 8080:8080 
           -v ~/scratch:/scratch/
           rvernica/scidb:18.1-ext /bin/bash
```

The above command will do the following:
1. Run SciDB CE on any OS (Mac / Windows / Unix) that has Docker running on it
2. Detach the process so that it continues to run in the background
3. Expose port 8080 so that one can connect from an external R / Python process to SciDB shim
4. Mount local directory `~/scratch/` as `/scratch`

## Attach to running container

```sh
# Find the container ID 
docker ps
# CONTAINER ID        IMAGE                     COMMAND                  ...
# ee1cbc462a0d        rvernica/scidb:18.1-ext   "/docker-entrypoint.…"   ...

# Attach to it
docker exec -i -t  ee1cbc462a0d /bin/bash
```

## Local computer

```sh
git clone https://github.com/paradigm4/accelerated_io_tools.git
git checkout v18.1_no_arrow
```

## Docker

```sh
make
```

## Local computer

Copy the `.so` into the relevant location of `gh-pages` branch

```sh
git clone -b gh-pages https://github.com/paradigm4/accelerated_io_tools aio_gh_pages
cd aio_gh_pages
# Add appropriate files to gh-pages branch
cp ../lib*.so rel18.1/ubuntu14/
# ... create new directories as needed
```

Recreate the index
```sh
# conda with python3
conda create --name gh-pages-index-creator
source activate gh-pages-index-creator
conda install mako

(gh-pages-index-creator) $ 
python ~/coding/make_index.py .
```

Add the changed files to `gh-pages` and then

```sh
git push origin gh-pages
```

Eventually we should consider distributing executables with some solution like [Bintray](https://bintray.com). See for example [Rares Vernica's bintray](https://bintray.com)
