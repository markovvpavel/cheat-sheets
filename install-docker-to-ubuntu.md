# Manual setup Docker in Ubuntu

This guide provides step-by-step instructions for installing Docker on an Ubuntu system, including setting up the repository, installing necessary components, and verifying the installation.

## Update the package index
```bash
sudo apt update
```

## Install required packages
```bash
sudo apt install -y ca-certificates curl gnupg lsb-release
```

## Create a directory for Docker's GPG key
```bash
sudo mkdir -p /etc/apt/keyrings
```

## Download and save Docker's official GPG key
```bash
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
```

## Add Docker's APT repository to the system's sources list
```bash
echo \
    "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
$(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list >/dev/null
```

## Update the package index again to include Docker's repository
```bash
sudo apt update
```

## Install Docker Engine, CLI, containerd, Buildx, and Compose plugins
```bash
sudo apt install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

## Verify Docker installation by checking its version
```bash
docker --version
```

## Verify Docker Compose plugin installation by checking its version
```bash
docker compose version