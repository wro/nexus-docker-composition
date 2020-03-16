### Description

This repository contains a docker composition which will spin up an OSS version of nexus3 in one container and an nginx reverse proxy in another.

### Launch

Launching the docker services is as simple as invoking:

```./start.sh```

By default a mount bind is set up using `/usr/share/nexus/data` as source. 
This value can be configured by providing the `NEXUS_DATA_VOLUME` environment variable.

Make sure that your bind mount has sufficient permissions for your container to access it.

This composition makes use of the following docker images:
sonatype/nexus3
nginx:alpine

```
mkdir /tmp/my-volume
sudo chown -R 200 /tmp/my-volume
export set NEXUS_DATA_VOLUME=/tmp/my-volume
./start.sh
```