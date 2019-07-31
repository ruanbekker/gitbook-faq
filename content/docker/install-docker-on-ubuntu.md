# Install Docker on Ubuntu

This guide will show you how to setup Docker Community Edition on Ubuntu

### Update Index Repositories

Update the repositories and get the dependencies:

```
$ sudo apt update 
$ sudo apt-get upgrade -y
$ sudo apt remove docker docker-engine -y
$ sudo apt install linux-image-extra-virtual -y
$ sudo apt install apt-transport-https ca-certificates curl software-properties-common -y
```

### Get the Docker Repository

Get the docker repositories and update your repository to get the sources:

```
$ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
$ sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
$ sudo apt update
```

### Install Docker

Install Docker, enable the service at boot and change the ownership so that a normal user can run docker commands:

```
$ sudo apt install docker-ce -y
$ sudo systemctl enable docker
$ sudo systemctl restart docker
$ sudo usermod -aG docker $(whoami)
```

### Test Docker

Run a container:

```
$ sudo docker run hello-world
```
