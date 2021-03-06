[![www.liferay.com](https://web.liferay.com/image/image_gallery?uuid=6f04350d-5873-48e2-88c8-200b48a77ad4&groupId=5912873&t=1325511154018)](https://www.liferay.com)

# Workshop - Docker machine

In this section we'll introduce `docker-machine`.

## Install Docker Toolbox

Download and install [Docker Toolbox](https://www.docker.com/docker-toolbox).

The toolbox installs a handful of tools on your local Windows or Mac OS X computer. In this exercise, you use two of those tools:

* Docker Machine: To deploy virtual machines that run Docker Engine
* VirtualBox: To host the virtual machines deployed from Docker Machine


## Create a VM running Docker

Open a terminal on your computer.

Create and run a VM named `default` using the following command:

```shell
docker-machine create -d virtualbox default
```

You can list the existing docker-machines:

```shell
docker-machine ls
```

In case you already had the machine created, you can simply start the VM:

```shell
docker-machine start default
```

## Run a docker container in a docker-machine

Now, let's use the docker-machine we've just created. We want to run the `hello-world`.

If you use Mac, you need to run:
```shell
eval $(docker-machine env default)
```

This command set the `DOCKER_HOST` variable to the IP of your `default` `docker-machine`.

Then we can run the `hello-world` container:
```shell
docker run hello-world
```

## Clean up

After we tested our `default` `docker-machine` we want to remove it from our computer.

Stop the VM named `default`:

```shell
docker-machine stop default
```

You can destroy the VM named `default`:

```shell
docker-machine rm default
```

## Create two machines

To create two machines do:

```shell
docker-machine create -d virtualbox client1
docker-machine create -d virtualbox client2
```

Now you can see the machines with:

```shell
docker-machine ls
```

## Run Nginx on client1

```shell
eval $(docker-machine env client1)
docker run -d -p 80:80 nginx:1.8-alpine
docker-machine ip client1
open "http://$(docker-machine ip client1)"
```

## Run Nginx on client2

```shell
eval $(docker-machine env client2)
docker run -d -p 80:80 nginx:1.8-alpine
docker-machine ip client2
open "http://$(docker-machine ip client2)"
```

## SSH to machine

To SSH inside a machine:

```shell
docker-machine ssh client1
```

To become `root` inside the machine:
```shell
sudo -i
```

## Active Machine

To get the active machine's name do:

```shell
docker-machine active
```

## Environment variables

Docker client is configured by environment variables to connect with remote daemons. The following command outputs the variables for connecting to previously created `client1` VM.

```shell
docker-machine env client1
```

## Cleanup


```shell
docker-machine stop client1 client2
docker-machine rm client1 client2
```


# Navigation

Previous | Next
:------- | ---:
← [Docker Workshop - Docker Basics](../00-docker-basics) | [Docker Workshop - Docker Compose](../02-docker-compose) →

# Credits

This workshop was prepared by [harbur.io](http://harbur.io), and adapted for Liferay's internal purpose by [Liferay, Inc.](https://www.liferay.com), under MIT License. Feel free to fork and improve.
