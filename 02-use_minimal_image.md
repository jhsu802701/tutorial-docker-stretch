# Chapter 2: Using the Minimal Docker Image

In this chapter, you will download the minimal Docker image, create a Docker container from it, and learn basic Docker capabilities.  This minimal image is a basic building block for other images and does NOT come with Ruby on Rails installed.  Because the minimal Docker image  Using Ruby on Rails in Docker will be covered in later chapters.

## Downloading the Image
* Download the repository for using Docker images by entering the following commands in a terminal:
```
cd
cd jhsu802701
git clone https://github.com/jhsu802701/docker-debian-stretch.git
cd docker-debian-stretch
```
* Note that there are scripts that create the files needed for each of the available Docker images.
* Create the files for using a Docker container based on the minimal Docker image.
  * If you are using 64-bit Linux, enter the following command:
  ```
  sh min.sh
  ```
  * If you are using 32-bit Linux, enter the following command:
  ```
  sh 32min.sh
  ```
  * Enter the following command to enter the directory for using the minimal image:
  ```
  cd min
  ```
  * Note that this "min" directory contains scripts for using a Docker container.  These scripts come with important parameters already filled in for you.  The 32min.sh script specifies the use of the 32-bit minimal image (jhsu802701/32bit-debian-stretch-min), while the min.sh script specifies the use of the 64-bit version of this image (jhsu802701/debian-stretch-min).
  * Note that this "min" directory contains a shared directory.  Files in these directories are accessible not only in your host environment but in your virtual Docker environment as well.  This will be demonstrated later in this chapter.
* Download the minimal Docker image and start a Docker container based on it by entering the following command:
```
sh download_new_image.sh
```
* The minimal Docker image will be downloaded, and a corresponding Docker container will be created. When the new Docker container is ready, you will be automatically logged in.
* When you are in the Docker container, enter the command "exit" to return to your desktop Linux system.

## Resume, Reset, and Download New Image
* The two scripts you will use most often to enter a Docker container are resume.sh and reset.sh.
* After you exit a Docker container, the resume.sh script allows you to re-enter.  Any changes you made to the Docker container since its creation from its Docker image are retained.
* The reset.sh script destroys your Docker container and creates a new one based on its Docker image.  Any changes you made to the Docker container are erased.
* The download_new_image.sh script destroys your Docker container, destroys its Docker image, and downloads a new Docker image.  In other words, this script does the same actions that the reset.sh script AND destroys the local Docker image.  If your Docker container is based on an outdated Docker image, this script updates it.

## Time Stamp File
* The time stamp file of a Docker container is /home/winner/timestamp.txt and is created during the build process.  Initially, the time stamp file includes the build date of the Docker image.  Every time you log into the Docker container, the date at which you did so is automatically added to the time stamp file.
* The content of the time stamp file is automatically printed out every time you log into a Docker container.

## Demonstation of Resume, Reset, and Download New Image
* From the min directory within the docker-debian-stretch project, enter the following command:
```
sh reset.sh
```
* Note that there is 

## Shared Directory Files

## Creating and Deleting Shared Directory Files

## Saving Shared Directory Files
