[![Docker Cloud Build Status](https://img.shields.io/docker/cloud/build/kijart/monit.svg)](https://hub.docker.com/r/kijart/monit)

# Monit - UNIX Systems Management

Run Monit inside docker.

[![Monit](https://mmonit.com/monit/img/logo.png)](https://mmonit.com/monit/)

[Monit](https://mmonit.com/monit/) is a free open source utility for managing and monitoring, processes, programs, files, directories and filesystems on a UNIX system. Monit conducts automatic maintenance and repair and can execute meaningful causal actions in error situations.

Default username/password: `admin/monit`

## Versions

| Docker image           | Monit     |
| ---------------------- | --------- |
| `kijart/monit:latest`  | `5.27.0`  |
| `kijart/monit:1.3.0`   | `5.27.0`  |
| `kijart/monit:1.2.0`   | `5.26.0`  |
| `kijart/monit:1.1.0`   | `5.25.2`  |
| `kijart/monit:1.0.2`   | `5.25.1`  |
| `kijart/monit:1.0.1`   | `5.25.1`  |
| `kijart/monit:1.0.0`   | `5.25.1`  |

## Docker setup

Install docker: <https://docs.docker.com/engine/installation/>

Install docker compose: <https://docs.docker.com/compose/install/>

Docker documentation: <https://docs.docker.com/>

### Build-in docker image

- build docker image `docker build -t monit .`

- start monit: `docker run --rm -it -p 2812:2812 -v $(pwd)/monitrc:/etc/monitrc monit`

### Docker Hub image

- pull docker image from docker hub: `docker pull kijart/monit:latest`

- start monit: `docker run --rm -it -p 2812:2812 -v $(pwd)/monitrc:/etc/monitrc kijart/monit:latest`

- create a docker container:

```bash
docker create \
  --name=monit \
  -p 2812:2812 \
  -v $(pwd)/monitrc:/etc/monitrc \
  kijart/monit:latest
```

### Docker compose

- create a container using docker-compose: `docker-compose up --no-start`

- start monit: `docker-compose up`

### Troubleshooting

If when starting Monit returns the following message: `The control file '/etc/monitrc' permission 0755 is wrong, maximum 0700 allowed`, simply give the appropriate permissions to _monitrc_: `chmod 700 monitrc`.
