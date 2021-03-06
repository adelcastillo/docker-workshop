[![www.liferay.com](https://web.liferay.com/image/image_gallery?uuid=6f04350d-5873-48e2-88c8-200b48a77ad4&groupId=5912873&t=1325511154018)](https://www.liferay.com)

# Docker Workshop

The Workshop is separated in three sections:

* [Docker Basics](doc/00-docker-basics)
* [Docker Machine](doc/01-docker-machine)
* [Docker Compose](doc/02-docker-compose)

### Preparations:

* If you don't know anything about Docker, please see [this presentation](http://www.slideshare.net/ManueldelaPeaPea/docker-zero).
* [Install Docker](https://docs.docker.com/engine/installation/)
* Clone this repo: `git clone https://github.com/mdelapenya/docker-workshop` (Some code examples require files located here)
* Warm-up the images:

```
docker pull alpine:3.3
docker pull nginx:1.8-alpine
docker pull redis:alpine
docker pull mhart/alpine-node:latest
```

### Assumptions:

* During workshop the following ports are used: `80`, `8088` and the range `4000-4010`. If they are not available on your machine, adjust the CLI commands accordingly.

### Docker Cheat Sheet:

Harbur's team wrote a page with some useful docker commands: [Harbur's docker-cheat-sheet](https://github.com/harbur/docker-cheat-sheet).

# Credits

This workshop was prepared by [harbur.io](http://harbur.io), and adapted for Liferay's internal purpose by [Liferay, Inc.](https://www.liferay.com), under MIT License. Feel free to fork and improve.
