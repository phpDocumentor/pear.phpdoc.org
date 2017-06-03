Pear Channel for phpDocumentor
==============================

In this repository you will find the sources for building the phpDocumentor 
PEAR channel.

## Usage

Add the PEAR package for phpDocumentor to this repository using the following
naming convention:

    phpDocumentor-[VERSION].tgz

Version needs to be the full semantic version without a `v` prefix, e.g. 
`3.0.0`.

As soon as the new package is pushed to the repository a Docker Container is
automatically built on Docker Hub and deployed to our cluster.

## Building and running the Docker Container

As part of QA you may want to build the container and run it to check if the
new version will be added correctly, this can be done using the following 
commands:

Building:

```
docker build -t phpdoc/pear.phpdoc.org .
```

Running:

```
docker run -d -p 8001:80 phpdoc/pear.phpdoc.org
```

As soon as you have executed the latter command you can open `localhost:8001` 
to check the web interface. You can even add it as a PEAR channel to verify 
that you can install from that location.
