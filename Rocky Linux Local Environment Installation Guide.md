
# Getting Started - Rocky Linux Local Environment Setup Guide - Fall 2025

## Table of Contents
- [Purpose](#purpose)
- [Terms and Definitions](#terms-and-definitions)
- [System Requirements](#system-requirements)
    - [Operating System Requirements](#operating-system-requirements)
    - [Recommended Browsers](#recommended-browsers)
    - [Minimum System Hardware Requirements](#minimum-system-hardware-requirements)
    - [Software Requirements](#software-requirements)
- [Rocky Linux Local Development Environment Setup](#rocky-linux-local-development-environment-setup)
    - [Download and Install Your IDE](#download-and-install-your-ide)
    - [Download and Install NVM and Node](#download-and-install-nvm-and-node)
    - [Download and Install Git](#download-and-install-git)
    - [Download and Install Composer](#download-and-install-composer)
    - [Download and Install PHP](#download-and-install-php)
    - [Download and Install Docker](#download-and-install-docker)
    - [Download and Install Docker Compose](#download-and-install-docker-compose)
    - [Clone CoRA Project from GitHub](#clone-cora-project-from-github)
    - [Create the env File](#create-the-env-file)
    - [Install Laravel Sail Components](#install-laravel-sail-components)
    - [Accessing CoRA Development Environment](#accessing-cora-development-environment)
    - [Accessing CoRA Web Interface](#accessing-cora-web-interface)

---

## Purpose
The purpose of this document is to describe the architecture, design, technical dependencies, and configuration steps required to set up the Commingled Remains Analytics (CoRA) web application locally on **Rocky Linux**.

## Terms and Definitions
The CoRA web application, database, and APIs are a community resource for inventorying assemblages of commingled human remains. This platform provides visualization tools, analytic methods, and a structured workflow for researchers.

---

## System Requirements

### Operating System Requirements
- Rocky Linux 9 or higher

### Recommended Browsers
CoRA is a browser-based application:
- Google Chrome *(Recommended)*
- Mozilla Firefox
- Microsoft Edge *(Optional)*

### Minimum System Hardware Requirements

| Hardware          | Minimum    | Recommended       | Notes |
| ----------------- | ---------- | ----------------- | ----------------------------- |
| **RAM**          | 8 GB       | 16+ GB            | Required for smooth Docker performance |
| **Screen Resolution** | 1024x768 | 1920x1080       | Ensures proper display of the UI |
| **CPU Cores**    | 2          | 4+ Cores          | Containers and PHP processes benefit from multiple cores |
| **Free Disk Space** | 4 GB     | 8+ GB            | For code, dependencies, and container images |
| **Disk Type**    | HDD        | SSD               | SSD recommended for performance |

### Software Requirements
- Git
- PHP (8.0 or higher)
- Composer
- Node.js & NVM
- Docker & Docker Compose
- IDE (e.g., VSCode or PHPStorm)

## Rocky Linux Local Development Environment Setup

### Download and Install Your IDE
We recommend using **VSCode** or **PHPStorm**:
```bash
sudo dnf install code -y
```
For **PHPStorm**, you can download it at [https://www.jetbrains.com/phpstorm/](https://www.jetbrains.com/phpstorm/).

### Download and Install NVM and Node
```bash
# Install NVM
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.3/install.sh | bash

# Reload your shell
source ~/.bashrc

# Verify installation
nvm --version

# Install Node.js LTS
nvm install --lts
```

### Download and Install Git
```bash
sudo dnf install git -y
git --version
```

### Download and Install Composer
```bash
sudo dnf install php-cli unzip curl -y
curl -sS https://getcomposer.org/installer -o composer-setup.php
sudo php composer-setup.php --install-dir=/usr/local/bin --filename=composer
composer --version
```

### Download and Install PHP
```bash
sudo dnf install php php-cli php-mbstring php-xml php-pgsql php-bcmath php-gd php-curl unzip -y
php -v
```

### Download and Install Docker
```bash
# Add Docker repo
sudo dnf config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo

# Install Docker
sudo dnf install docker-ce docker-ce-cli containerd.io -y

# Enable & Start Docker
sudo systemctl enable --now docker

# Add current user to Docker group
sudo usermod -aG docker $USER

# Verify installation
docker --version
```

### Download and Install Docker Compose
```bash
sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose

sudo chmod +x /usr/local/bin/docker-compose
docker-compose --version
```

### Clone CoRA Project from GitHub
```bash
git clone https://github.com/SachinPawaskarUNO/cora25.git
cd cora25
```

### Create the env File
```bash
cp .env.example .env
```

Update `.env` with your database credentials.

### Install Laravel Sail Components
```bash
composer install
./vendor/bin/sail up -d
```

### Accessing CoRA Development Environment
```bash
./vendor/bin/sail up -d
./vendor/bin/sail shell
npm install
```

### Accessing CoRA Web Interface
After starting Laravel Sail, open your browser and go to:
```
http://127.0.0.1:8000
```

# Congratulations! 🎉  
You've successfully set up the CoRA Project Development Environment on Rocky Linux!
