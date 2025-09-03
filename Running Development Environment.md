# Running the CORA Development Environment

## Table of contents
- [Purpose](#purpose)
- [Terms and Definitions](#terms-and-definitions)

## Purpose
The purpose of this document is to assist technicians in regards to running the development environment once their local machines have been setup and configured.

## Terms and Definitions
The CoRA web application, database and APIs are a community resource for inventorying assemblages of commingled human remains which are often encountered in archaeological and forensic contexts, while providing a framework of analytic methods, visualization techniques and tools to assist in the segregation and identification process. The application is an enhancement of existing CoRA web application layout, in order to bring progressive front-end design for the users. These enhancements for the application will allow users to access the website and use the full range of application features since it embraces both the desktop and mobile universes with responsiveness, flexibility, and extensibility.

## System Requirements
 
- [Running the Development Environment](#running-the-development-environment)
- [Accessing CORA Web Interface](#accessing-cora-web-interface)

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

### Running the Development Environment
*Note: You will need to follow the documentation that has been provided regarding the initial setup of the development environment for your respective system type*

*Note: All of the following commands are run in the Unbuntu terminal under the CoRA project root directory*

1. Start the docker container by navigating to the CoRA project root directory

</br>

		./vendor/bin/sail up -d

*Note: This step may take some time.*

2. Once the docker container is up and running, install the additional required components into the shell of the docker container
	in the CoRA project root directory, after *./vendor/bin/sail up* has been run.

</br>

		./vendor/bin/sail shell
		npm install

3. If you are running file import functionality for local testing, open new terminal and run

	./vendor/bin/sail shell
	php artisan horizon

If you want to monitor the file import jobs, Please open a browser and navigate to `localhost/horizon`.
4. You will now be able to open up a browser and navigate to local host.

### Accessing CORA Web Interface

*Note: All of the following commands are run in the Ubuntu terminal*

1. Start the development server by running the following command:

</br>

		php artisan serve

2. Access the web page by going to 127.0.0.1:8000 within your browser

# Congratulations! You've successfully setup the CoRA Project Development Environment!
