# Monit - UNIX Systems Management

Run Monit inside docker.

[![Monit](https://mmonit.com/monit/img/logo.png)](https://mmonit.com/monit/)

[Monit](https://mmonit.com/monit/) is a free open source utility for managing and monitoring, processes, programs, files, directories and filesystems on a UNIX system. Monit conducts automatic maintenance and repair and can execute meaningful causal actions in error situations.

## Docker setup

Install docker: https://docs.docker.com/engine/installation/

Docker documentation: https://docs.docker.com/

### Build-in docker image

- build docker image `docker build -t monit .`

- start monit: `docker run -ti -p 2812:2812 -v $(pwd)/monitrc:/etc/monitrc monit`

### Docker Hub image

- pull docker image from docker hub: `docker pull kijart/monit`

- download a video using docker image: `docker run -ti -p 2812:2812 -v $(pwd)/monitrc:/etc/monitrc kijart/monit`

- create a docker container:

```
docker create \
  --name=monit \
  -p 2812:2812 \
  -v $(pwd)/monitrc:/etc/monitrc \
  kijart/monit
```

### Troubleshooting

If when starting Monit returns the following message: `The control file '/etc/monitrc' permission 0755 is wrong, maximum 0700 allowed`, simply give the appropriate permissions to _monitrc_: `chmod 700 monitrc`.
