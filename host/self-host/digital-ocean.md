---
title: 'Deploy Terapi with Digital Ocean (Droplet)'
sidebarTitle: 'Digital Ocean'
---


These instructions only apply for **free** self-hosting features, not Enterprise features ([feature list]()).

Read the [self-hosting instructions](/host/self-host/self-hosting-instructions) before deploying to production.

## Create a VM[](#create-vm 'Direct link to Create a VM')

Go to [DigitalOcean](https://cloud.digitalocean.com/) and click _CREATE >
Droplets_. Create a default VM instance with options:

-   \$20/month for testing, \$40/month for production

## Install Docker[](#install-docker 'Direct link to Install Docker')

Go to your Droplet instance page and click _Console_.

Install Docker & Docker Compose with the following commands:

```bash
sudo apt-get update && sudo apt-get install -y apt-transport-https ca-certificates curl gnupg2 software-properties-common wget
curl -fsSL https://download.docker.com/linux/debian/gpg | sudo apt-key add --
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/debian buster stable"
sudo apt-get update
sudo apt-get install -y docker-ce docker-ce-cli containerd.io
sudo usermod -a -G docker $USER
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

