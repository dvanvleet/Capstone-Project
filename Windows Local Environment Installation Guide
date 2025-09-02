# Getting Started - Windows Local Environment Setup Guide - Fall 2025

## Table of contents
- [Purpose](#purpose)
- [Terms and Definitions](#terms-and-definitions)

## System Requirements
 
- [Operating System Requirements](#operating-system-requirements)
- [Recommended Browsers](#recommended-browsers)
- [Minimum System Hardware Requirements](#minimum-system-hardware-requirements)
- [Software Requirements](#software-requirements)

### Windows Local Environment Setup
- [Windows Local Development Environment Initial Setup](#windows-local-development-environment-initial-setup)
- [Download and Install Oracle VM VirtualBox](#download-and-install-oracle-vm-virtualbox) 
- [Download and Install Ubuntu Desktop into VirtualBox](#download-and-install-ubuntud-desktop-into-virtualbox)
- [Download and Install WSL (Windows Subsystem for Linux)](#download-and-install-wsl)
- [Download and Install your IDE of Choice](#download-and-install-vagrant)
- [Download and Install Composer](#download-and-install-composer)
- [Download and Install Git](#download-and-install-git)
- [Download and Install PHP](#download-and-install-php)
- [Download and Install Docker](#download-and-install-docker)
- [Download and Install Docker Compose](#download-and-install-docker-compose)
- [Clone CoRA Project from cora25 GitHub Repository](#clone-cora-project-from-cora25-gitHub-repository)
- [Create the env File](#create-the-env-file)
- [Install the Laravel Sail components required to start the container using Composer](#install-the-laravel-sail-components-required-to-start-the-container-using-composer)
- [Accessing CORA Development Environment](#accessing-cora-development-environment)

## Purpose
The purpose of this document is to describe the architecture, design, technical dependencies, key configurations, specifications used to develop the existing Commingled Remains Analytics (CoRA) web application for Defense POW/MIA Accounting Agency (DPAA). The document will provide a clear understanding of how to set up the system locally, configurations for the testing environment, and any potential issues that may arise and how to resolve them.

## Terms and Definitions
The CoRA web application, database and APIs are a community resource for inventorying assemblages of commingled human remains which are often encountered in archaeological and forensic contexts, while providing a framework of analytic methods, visualization techniques and tools to assist in the segregation and identification process. The application is an enhancement of existing CoRA web application layout, in order to bring progressive front-end design for the users. These enhancements for the application will allow users to access the website and use the full range of application features since it embraces both the desktop and mobile universes with responsiveness, flexibility, and extensibility.

## System Requirements

### Operating System Requirements

- Microsoft Windows - Windows 10 or higher
- Apple - Mac OS 10.5 or higher 
- Linux - Ubuntu 20.04

### Recommended Browsers

CoRA is a web browser-based application which can be accessed through a browser on a computer or a mobile device. It is recommended that the browsers being used are compatible with HTML5 and CSS3.  

#### Desktop/Laptop Browsers
- Google Chrome
- Microsoft Edge

*Note: CoRA may work with Mozilla Firefox and Safari however it has not been thorougly tested at the time of this documentation.*

#### Mobile Browsers
- Google Chrome

*Note: CoRA may work with Mozilla Firefox and Safari however it has not been thorougly tested at the time of this documentation.*

### Minimum System Hardware Requirements
*Note: The minimum requirement meets the requirement to get the system up and running. However, you will notice serious performance degradation when just meeting minimum requirements not using recommended requirements.*

| Hardware          | Minimum    | Recommended       | Notes                                                                                                                                              |
| ----------------- | ---------- | ----------------- | -------------------------------------------------------------------------------------------------------------------------------------------------- |
| RAM               | 8 GB      | 16+ GB             | Running a development environment consumes significant RAM, 8 GB will give you decent performance and 16 GB will give you a better experience      |
| Screen Resolution | 1024x768   | 1920x1080         |   To allow proper viewing of the site                                                                                                                                                 |
| CPU Cores         | 2          | 4+ Cores          | Running a VM for VirutalBox will require consuming parts of your CPU cores, the more you have the better performance you will receive                 |
| Free Disk Space   | 4 GB       | 8+ GB             | Code is ~2 GB, VirtualBox is 217 MB, Node.js is 54.2 MB, space is also needed for cache                                                                            |
| Disk Type         | Hard Drive | Solid State Drive | SSD does not require mechanical spinning drives which is known for slowing down systems, SSD runs much faster than standard mechanical hard drives |

### Software Requirements

Linux support

## Windows Local Development Environment Initial Setup

This documentation was created in Fall 2025 at the time of CoRA version 2.5. Hereby noted as "cora25." This documentation is resuming under the assumption that the reader has technical proficency. You may either deploy via a virtual machine within Vritual Box or utilize WSL.

### Download and Install Oracle VM VirtualBox

*Note: Oracle VM VirtualBox version 6.1.26 as of September 26, 20201*

1. Download Oracle VM VirtualBox version 6.1.26 at: [https://www.virtualbox.org/wiki/Downloads](https://www.virtualbox.org/wiki/Downloads)

2. Choose "Windows hosts"

3. After the application has been downloaded, proceed with the installation
	- At the "Custom Setup" screen leave everything as default and choose Next
	- At the 2nd "Custom Setup" screen, leave everything as default and choose Next
	- At the "Warning: Network Interfaces" screen, click yes to proceed with the installation now
	- A prompt will appear asking you to install Oracle USB software, choose install

### Download and Install Ubuntu Desktop into VirtualBox
*Note: You will be installing an Ubuntu OS onto the VM created in VirtualBox*

1. Download Ubuntu Desktop 20.04 (https://ubuntu.com/download/desktop)

2. Open Virutal Box and select "new"
	- Name the VM
	- Select the desired machine folder.
	- Type: Linux
	- Version: Ubuntu (64bit)
	- Select a Memory size of at least 8GB
	- Create a Virtual Hard Disk of at least 30GB

3. Start the Virtual Machine
	- Select the Ubuntu Desktop OS you downloaded as the start up disk
	- Install Ubantu Desktop as minimal
	
	*Note: Installing the full Ubuntu desktop may cause conflict with the Ubuntu apache2 webserver*

4. Upgrade Ubuntu to the most recent update
	- Open terminal

</br>

		sudo apt update
		sudo apt upgrade

5. Install additional repositories

*Note: CoRA requires additional Ubuntu repositories to function*

</br>

		sudo add-apt-repository universe
		sudo add-apt-repository multiverse

### Download and Install WSL
*Note: You will be installing WSL onto your local machine within a Windows terminal*

1. Launch a Terminal Window

2. Run the command: wsl --install -d Ubuntu

3. Restart your machine

*Note: If this does not work, try the following steps to install WSL*

1. Launch the Microsoft Store

2. Find the latest LTS version for Ubuntu and install it

3. Open Terminal and run the following commands:
		a. dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
		b. dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart

4. Restart your machine

5. Open a terminal window and run wsl --update and ensure that it is at the latest version

6. Close the terminal and relaunch

7. Upgrade Ubuntu to the most recent update
	- Open terminal

</br>

		sudo apt update
		sudo apt upgrade

8. Install additional repositories

*Note: CoRA requires additional Ubuntu repositories to function*

</br>

		sudo add-apt-repository universe
		sudo add-apt-repository multiverse

### Download and Install your IDE of Choice 
*Note: recommended IDE is VSCode or PHPStorm*

1. As a UNO Student, PhpStorm is free. You can apply for a free license with JetBrains using your UNO email address at: https://www.jetbrains.com/community/education/#students. This will allow you to license your PhpStorm software at no cost and last beyond the 30 day trial period.

	After applying for the license and receiving a confirmation email. You can install PhpStorm at: https://www.jetbrains.com/phpstorm/.  

	Alternatively, you can download the PhpStorm software from your JetBrains account that is created after signing up at: https://account.jetbrains.com/licenses

2. Download and install your IDE of choice to Ubuntu

### Download and Install Composer

*Note: Please refer to the following link for information on installing and using Composer in Ubuntu 20.04: https://www.digitalocean.com/community/tutorials/how-to-install-and-use-composer-on-ubuntu-20-04*

*Note: All of the following commands are run in the Unbuntu terminal*

1. Run the following command to install required packages for Composer:

</br>

		sudo apt install php-cli unzip

2. Downloading and installing Composer

</br>

		sudo apt install curl
		curl -sS https://getcomposer.org/installer -o composer-setup.php
		sudo php composer-setup.php --install-dir=/usr/local/bin --filename=composer

3. Check that the correct version of Composer was installed

</br>

		composer --version

### Download and Install Git
*Note: Git is Required for version control in the CoRA project.*

*Note: All of the following commands are run in the Unbuntu terminal*

1. Install Git

</br>

		sudo apt install git

### Download and Install PHP
*Note: PHP 8.0 or PHP 7.4 are the required versions for the project*

*Note: All of the following commands are run in the Unbuntu terminal*

1. OPTION 1: To install PHP 7.4

</br>

		sudo apt install php-cli php-mbstring php-xml php-dom php-zip php-curl php-gd

2. OPTION 2: To install PHP 8.0

</br>

		sudo apt install software-properties-common 
		sudo add-apt-repository ppa:ondrej/php 
		sudo apt update 
		sudo apt-get upgrade 
		sudo apt install php8.0 php8.0-cli  
		sudo apt install php8.0-mbstring php8.0-dom php8.0-zip php8.0-curl php8.0-xml php8.0-gd

### Download and Install Docker
*Note: All of the following commands are run in the Unbuntu terminal*

1. Check for updates

</br>

		sudo apt-get update 

2. Install Docker

</br>

		sudo apt-get install apt-transport-https ca-certificates curl gnupg lsb-release 
		curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg 
		echo \ "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null 
		sudo apt-get update 
		sudo apt-get install docker-ce docker-ce-cli containerd.io 

3. Configure Docker to start on boot

</br>

		sudo usermod -aG docker $USER 
 		sudo systemctl start docker 
 		sudo chmod -R 777 /var/lib/docker 

4. Restart Ubuntu

</br>

		sudo reboot

5. Verify Docker installation

</br>

		docker --version

### Download and Install Docker Compose
*Note: All of the following commands are run in the Unbuntu terminal*
1. Install Docker Compose

</br>

		sudo curl -L "https://github.com/docker/compose/releases/download/1.27.4/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose 
		sudo chmod +x /usr/local/bin/docker-compose

2. Verify Docker Compose installation

</br>

		docker-compose --version

### Clone CoRA Project from cora25 GitHub Repository
*Note: This step required a developer access token (https://github.com/settings/tokens)*

*Note: All of the following commands are run in the Unbuntu terminal*

1. Clone the project

</br>

		git clone https://github.com/SachinPawaskarUNO/cora25.git

2. You may be prompted to log into your GitHub account, proceed with logging in.

*Note: The github password will be the developer access token, NOT your github password*

3. The project will download and it may take a while.

### Create the env File

1. You will not be able to open the development environment until you receive the database credentials and instructions on what to enter in the .env file.

2. Once you receive the information needed to put in your .env file, in the file explorer, navigate to */cora25/.env.example*. Update the file as directed and save the file as ".env"

3. Change REDIS_HOST value from 127.0.0.1 to redis.

### Install the Laravel Sail components required to start the container using Composer

*Note: All of the following commands are run in the Unbuntu terminal*

*Note: It is normal and expected to receive unconsequential errors after this step*

1. Navigate to the project directory

*Note: Your terminal should now be in the project directory*

2. Run the composer update command to update composer

</br>

		composer update

### Accessing CORA Development Environment

*Note: All of the following commands are run in the Unbuntu terminal under the CoRA project root directory*

1. Start the docker container by navigating to the CoRA project root directory

</br>

		./vendor/bin/sail up

*Note: This step may take some time.*

2. Once the docker container is up and running, install the additional required components into the shell of the docker container
	in the CoRA project root directory, after *./vendor/bin/sail up* has been run.

</br>

		./vendor/bin/sail shell
		npm install

3. If you are running file import functionality for local testing, open new terminal and run
```
	./vendor/bin/sail shell
	php artisan horizon
```
If you want to monitor the file import jobs, Please open a browser and navigate to `localhost/horizon`.
4. You will now be able to open up a browser and navigate to local host.

# Congratulations! You've successfully setup the CoRA Project Development Environment!
