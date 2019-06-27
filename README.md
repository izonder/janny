# JANNY - a slim docker container image with Java

**JANNY** = **J**ava + **A**lpine + **N**ginx + **N**ode.js + **Y**arn

[![](https://images.microbadger.com/badges/version/izonder/janny.svg)](https://microbadger.com/images/izonder/janny "Get your own version badge on microbadger.com")
[![](https://images.microbadger.com/badges/image/izonder/janny.svg)](https://microbadger.com/images/izonder/janny "Get your own image badge on microbadger.com")
[![Build Status](https://travis-ci.org/izonder/janny.svg?branch=master)](https://travis-ci.org/izonder/janny)

## Features

- Alpine linux as base-image
- S6-overlay to run multiple processes in container
- Nginx with basic configuration
- Node.js v10.x.x
- Yarn package manager
- Java OpenJDK 8 (JRE)

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
