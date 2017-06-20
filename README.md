# docker-hugo

[![Docker Build Status](https://img.shields.io/docker/build/yanqd0/hugo.svg)](https://hub.docker.com/r/yanqd0/hugo/builds/)
[![Docker Automated build](https://img.shields.io/docker/automated/yanqd0/hugo.svg)](https://hub.docker.com/r/yanqd0/hugo/builds/)
[![Docker Stars](https://img.shields.io/docker/stars/yanqd0/hugo.svg)](https://hub.docker.com/r/yanqd0/hugo/)
[![Docker Pulls](https://img.shields.io/docker/pulls/yanqd0/hugo.svg)](https://hub.docker.com/r/yanqd0/hugo/)

A hugo docker image built from Alpine.

## Install

```sh
docker pull yanqd0/hugo
```

Docker Hub: <https://hub.docker.com/r/yanqd0/hugo/>

## Usage

There are two simple ways to use it, `docker run` or `docker-compose up`.

### docker run

In the hugo project, execute the command below:

```sh
docker run -v $PWD:/srv/hugo -p 1313:1313 yanqd0/hugo
```

If your current directory is not your hugo project, you can replace `$PWD` with the path.

### docker-compose up

It is not a good way to use `docker run` in your production environment.

I prefer to use a [docker-compose.yml file].

You can write a `docker-compose.yml` in your hugo project like this:

```yaml
version: '3'

services:
  hugo:
    image: yanqd0/hugo
    volumes:
      - .:/srv/hugo
    ports:
      - 1313:1313
```

And then, run `docker-compose up -d`.

There is a verified [docker-compose.yml] for example.

[![Build Status](https://travis-ci.org/yanqd0/docker-hugo.svg?branch=master)](https://travis-ci.org/yanqd0/docker-hugo)

[docker-compose.yml file]:https://docs.docker.com/compose/compose-file/
[docker-compose.yml]:https://github.com/yanqd0/docker-hugo/blob/master/docker-compose.yml

## License

[![License](https://img.shields.io/github/license/yanqd0/docker-hugo.svg)](https://github.com/yanqd0/docker-hugo/blob/master/LICENSE)

> The MIT License (MIT)
>
> Copyright (c) 2017 yanqd0@outlook.com
