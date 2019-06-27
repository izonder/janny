# JANNY - a slim docker container image with Java

**JANNY** = **J**ava + **A**lpine + **N**ginx + **N**ode.js + **Y**arn

[![](https://images.microbadger.com/badges/version/izonder/janny.svg)](https://microbadger.com/images/izonder/janny "Get your own version badge on microbadger.com")
[![](https://images.microbadger.com/badges/image/izonder/janny.svg)](https://microbadger.com/images/izonder/janny "Get your own image badge on microbadger.com")
[![Build Status](https://travis-ci.org/izonder/janny.svg?branch=master)](https://travis-ci.org/izonder/janny)

## IMPORTANT! Breaking changes announcement

Due to new JDK verion we have released a major upgrade, which contains:
- [OpenJDK 11](https://openjdk.java.net/projects/jdk/11/)
- [Parent package v12](https://hub.docker.com/r/izonder/anny/)

Please be aware of that and make sure these changes won't affect your functionality. Also be aware the child image [`izonder/lanny`](https://hub.docker.com/r/izonder/lanny/) is also rebuilt based on `izonder/janny:latest`.

## Supported tags and respective `Dockerfile` links
- `latest` [(Dockerfile)](https://github.com/izonder/janny/blob/master/Dockerfile)
- `12` [(Dockerfile)](https://github.com/izonder/janny/blob/nodejs-12/Dockerfile)

## Features

- Alpine linux as base-image
- S6-overlay to run multiple processes in container
- Nginx v1.16.x with basic configuration
- Node.js v12.x.x
- Yarn package manager
- Java OpenJDK 11 (JRE)

## How to use?

```
FROM izonder/anny:latest

...

# add new service
COPY ./service/myservice.sh /etc/services.d/myservice/run

...

# add nginx configuration
COPY ./nginx/myapp.conf /etc/nginx/conf.d/myapp.conf

...

# install dependencies
RUN yarn install

...

# run java
RUN java [parameters]

...

# entry point
CMD ["node", "myapp.js"]
```
