# Prometheus Ubuntu

## Install Docker
```
sudo apt update
sudo apt install -y docker.io

####### RUN DOCKER WITHOUT SUDO
sudo usermod -aG docker $USER
newgrp docker
```

## Install Docker Compose
Just Blindly Copy Paste next 4 lines and then again next 7 lines
```
sudo apt-get -y install ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc

# Add the repository to Apt sources:
echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update

sudo apt-get -y install docker-compose-plugin
```

## Run the Prometheus & Grafana
`docker compose up -d`

These 3 services should now be running

NodeExporter on port 9901

Prometheus on port 9902

Grafana on port 9903
