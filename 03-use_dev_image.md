# Chapter 3: Using the Development Image
[** Click here for Chapter 2 ** ](https://github.com/rubyonracetracks/tutorial-docker-stretch/blob/master/02-use_minimal_image.md)
In this chapter, you will download the development Docker image and learn more of the basic capabilities of Docker.  This development image is a derivative of the minimal image used in the previous chapter but has basic software development tools added, such as Git, Heroku, Node Version Manager, Node.js, Python, and rbenv.

## Topics Covered
* Time stamp file
* Removing and restoring Node.js in seconds
* Nuking all Docker images from your system

## Downloading the Image
* In your desktop Linux system, enter the following commands in a terminal:
```
cd
cd rubyonracetracks
cd docker-debian-stretch # Back to the docker-debian-stretch repository from the previous chapter
```
* Enter the command "ls" to see the available scripts.
* Create the files for using a Docker container based on the development Docker image.
  * If you are using 64-bit Linux, enter the following command:
  ```
  sh dev.sh
  ```
  * If you are using 32-bit Linux, enter the following command:
  ```
  sh 32dev.sh
  ```
  * Enter the following command to enter the directory for using the development image:
  ```
  cd dev
  ```
  * Enter the command "ls".  Note that this "dev" directory contains scripts for using the rubyonracetracks/32bit-debian-stretch-dev or rubyonracetracks/debian-stretch-dev Docker image.  Again, these scripts come with important parameters already filled in for you.
  * Enter the command "ls shared".  You can see the files within the shared directory.
* Download the development Docker image and start a Docker container based on it by entering the following command:
```
sh download_new_image.sh
```
* The development Docker image will be downloaded, and a corresponding Docker container will be created. When the new Docker container is ready, you will be automatically logged in.
* When you are in the Docker container, enter the command "exit" to return to your desktop Linux system.

## Information
* Enter the command "sh reset.sh".
* Enter the command "sh info.sh".  You'll see information on the software included in this Docker image.
* Enter the command "exit".

## Time Stamp
* Enter the command "sh reset.sh".
* Note that the time stamp file has two build dates instead of one.  That's because the development Docker image is a derivative of the minimal Docker image.  The first date is the time at which the minimal Docker image was built, and the second date is the time at which the development Docker image (the one based on your current Docker container) was built.

## Removing and Restoring Node.js
* Enter the command "node -v".  You'll see that Node.js is installed.
* Enter the command "rm -rf /home/winner/.nvm".  Yes, you are removing Node.js.  This is NOT an action to use in a development environment on a host system.
* Enter the command "node -v".  You'll see that Node.js is no longer installed, because you deleted it.
* Enter the command "exit".
* Enter the command "sh resume.sh".
* Enter the command "node -v".  Node.js is still gone.
* Enter the command "exit".
* Enter the command "sh reset.sh".  
* Enter the command "node -v".  Your installation of node.js has been restored in just a few seconds.  If you had removed Node.js in this manner on your host system, you'd need several minutes to reinstall it.
* Enter the command "exit".

## Nuking All Docker Images
* From the desktop Linux system, enter the command "docker ps -a".  You'll see a list of Docker containers, including the containers from the minimal image that you used in the previous chapter.
* Enter the command "docker images -a".  You'll see a list of Docker images, including the minimal image from the previous chapter.
* Enter the command "sh nuke.sh".  This removes all Docker containers and images.
* Enter the command "docker ps -a".  You'll see no Docker containers.
* Enter the command "docker images -a".  You'll see no Docker images.
[** Click here for Chapter 4 ** ](https://github.com/rubyonracetracks/tutorial-docker-stretch/blob/master/04-use_jekyll_image.md)
