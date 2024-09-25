---
title: 'Deploy Terapi with AWS (EC2)'
sidebarTitle: 'AWS'
---


These instructions only apply for **free** self-hosting features, not Enterprise features ([feature list]()).

Read the [self-hosting instructions](/host/self-host/self-hosting-instructions) before deploying to production.

## Create a VM[](#create-vm 'Direct link to Create a VM')

Go to the [EC2 service](https://console.aws.amazon.com/ec2/v2/home) and click
_Launch Instance_. Create an instance with default settings except:

-   `t2.medium` for testing, `t2.large` for production
-   Enable _Allow HTTPS traffic from the internet_ and _Allow HTTP traffic from
    the internet_

## Install Docker[](#install-docker 'Direct link to Install Docker')

Go to your EC2 instance page and click _Connect,_ then _Connect_ again on the
next page to access your instance’s console via SSH.

Install Docker & Docker Compose with the following commands:

```bash
sudo yum update -y && sudo yum install -y docker && sudo service docker start && sudo usermod -a -G docker $USER
curl -s https://api.github.com/repos/docker/compose/releases/latest | grep browser_download_url  | grep docker-compose-linux-x86_64 | cut -d '"' -f 4 | wget -qi -
chmod +x docker-compose-linux-x86_64 && sudo mv docker-compose-linux-x86_64 /usr/local/bin/docker-compose
docker-compose --version
```

Refresh the VM console page to activate the new configuration.

## Run Terapi[](#run-terapi 'Direct link to Run Terapi')

Still in your VM’s console, install Terapi by running:

```bash
mkdir terapi && cd terapi
wget https://raw.githubusercontent.com/NangoHQ/nango/master/docker-compose.yaml
docker-compose up -d # Terapi is now running!
```

## Update Terapi[](#update-terapi 'Direct link to Update Terapi')

In your VM’s console, run:

```bash
docker-compose stop
docker-compose rm -f
docker-compose pull
docker-compose up -d
```


