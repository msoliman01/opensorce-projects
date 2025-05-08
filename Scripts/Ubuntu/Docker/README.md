# Docker Installation Script for Ubuntu

This repository contains a Bash script to install Docker and its dependencies on Ubuntu Linux. The script automates the official Docker installation process by removing old versions, adding Docker's GPG key, setting up the repository, and installing the latest Docker packages.

## Prerequisites

- Ubuntu Linux (tested on 20.04 LTS, 22.04 LTS)
- `sudo` privileges
- Internet connection

## Usage

### 1. Download the Script

```bash
curl -O https://raw.githubusercontent.com/msolimantech1/open-source-projects/refs/heads/master/Scripts/Ubuntu/Docker/install_docker.sh
```

### 2. Make the Script Executable

```bash
chmod +x install_docker.sh
```

### 3. Run the Script

```bash
sudo ./install_docker.sh
```

### 4. Verify Installation (Optional)

After installation, verify Docker works by running:

```bash
sudo docker run hello-world
```

You should see a welcome message confirming Docker is installed correctly.

## What the Script Does

1. Removes any existing Docker packages
2. Updates package lists and installs dependencies
3. Adds Docker's official GPG key
4. Sets up the stable Docker repository
5. Installs:
   - Docker Engine
   - Docker CLI
   - Containerd
   - Docker Buildx Plugin
   - Docker Compose Plugin

## Post-Installation Steps (Recommended)

### Add Your User to the Docker Group

To run Docker commands without `sudo`:

```bash
sudo usermod -aG docker $USER
newgrp docker  # Activates the group changes without logout
```

### Enable Docker to Start on Boot

```bash
sudo systemctl enable docker.service
sudo systemctl enable containerd.service
```

## Troubleshooting

If you encounter issues:
- Check [Docker's official documentation](https://docs.docker.com/engine/install/ubuntu/)
- Ensure your system meets the requirements
- Verify no other Docker installations conflict

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
