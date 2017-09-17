# docker-node-sonos-http-api
Docker wrapper for https://github.com/jishi/node-sonos-http-api

[![GitHub issues](https://img.shields.io/github/issues/chrisns/docker-node-sonos-http-api.svg)](https://github.com/chrisns/docker-node-sonos-http-api/issues)
[![GitHub forks](https://img.shields.io/github/forks/chrisns/docker-node-sonos-http-api.svg)](https://github.com/chrisns/docker-node-sonos-http-api/network)
[![GitHub stars](https://img.shields.io/github/stars/chrisns/docker-node-sonos-http-api.svg)](https://github.com/chrisns/docker-node-sonos-http-api/stargazers)
[![GitHub license](https://img.shields.io/badge/license-MIT-blue.svg)](https://raw.githubusercontent.com/chrisns/docker-node-sonos-http-api/master/LICENSE)
[![Docker Stars](https://img.shields.io/docker/stars/chrisns/docker-node-sonos-http-api.svg)](https://hub.docker.com/r/chrisns/docker-node-sonos-http-api)
[![Docker Pulls](https://img.shields.io/docker/pulls/chrisns/docker-node-sonos-http-api.svg)](https://hub.docker.com/r/chrisns/docker-node-sonos-http-api)
[![Docker Automated buil](https://img.shields.io/docker/automated/chrisns/docker-node-sonos-http-api.svg)](https://hub.docker.com/r/chrisns/docker-node-sonos-http-api)
[![Docker Build Statu](https://img.shields.io/docker/build/chrisns/docker-node-sonos-http-api.svg)](https://hub.docker.com/r/chrisns/docker-node-sonos-http-api)
[![ImageLayers Size](https://img.shields.io/imagelayers/image-size/chrisns/docker-node-sonos-http-api/latest.svg)](https://hub.docker.com/r/chrisns/docker-node-sonos-http-api)
[![ImageLayers Layers](https://img.shields.io/imagelayers/layers/chrisns/docker-node-sonos-http-api/latest.svg)](https://hub.docker.com/r/chrisns/docker-node-sonos-http-api)

## Usage
Refer to https://github.com/jishi/node-sonos-http-api for all the configuration detail

First make the config and local dirs up
```shell
mkdir clips
mkdir settings
mkdir cache
mkdir presets
curl https://raw.githubusercontent.com/jishi/node-sonos-http-api/master/presets/example.json > presets/example.json
echo {} > settings/settings.json
```

Then run the docker image
```shell
docker run \
  --net=host \
  --name sonos \
  --restart=always \
  -d \
  -v `pwd`/settings:/app/settings \
  -v `pwd`/clips:/app/static/clips \
  -v `pwd`/cache:/app/cache \
  -v `pwd`/presets:/app/presets \
  chrisns/docker-node-sonos-http-api 
```