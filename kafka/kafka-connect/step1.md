
Description : Some tools installation.

## Create plugins folder

> Used in further `Connectors` step

```
mkdir plugins
```{{execute}}

## Install unzip, cURL and Wget

```
sudo apt-get install -y unzip curl wget
```{{execute}}

## Install docker

make this tutorial playable anywhere, we'll use [`docker`](https://www.docker.com/).

Then properly install it:

```
sudo apt-get remove docker docker-engine docker.io
sudo apt install docker.io
sudo systemctl start docker
sudo systemctl enable docker
```{{execute}}

`docker` is finally installed :

`docker --version`{{execute}}