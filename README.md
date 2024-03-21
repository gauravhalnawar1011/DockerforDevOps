# Docker Installation Guide for Ubuntu OS

This guide provides step-by-step instructions on how to install Docker on Ubuntu OS. Docker is a set of platform as a service (PaaS) products that use OS-level virtualization to deliver software in packages called containers.

## Prerequisites

- An Ubuntu system (We recommend using the latest LTS version)
- A user account with `sudo` privileges
- fo to https://docs.docker.com/ then https://docs.docker.com/manuals/ then https://docs.docker.com/engine/  --> install os the commands 

## Step 1: Update Your System for Ex Ubuntu

Before installing Docker, it's a good idea to update your package index and upgrade your system to ensure you have the latest versions of all your software.

```bash
sudo apt-get update
sudo apt-get upgrade
```

Install using the apt repository
Before you install Docker Engine for the first time on a new host machine, you need to set up the Docker repository. Afterward, you can install and update Docker from the repository.
```bash
# Add Docker's official GPG key:
sudo apt-get update
sudo apt-get install ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc

# Add the repository to Apt sources:
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update
```
## To install the latest version, run:
```bash
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```
## Verify that the Docker Engine installation is successful by running the hello-world image.

```bash
 sudo docker run hello-world
```

