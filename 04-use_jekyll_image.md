# Chapter 4: Using the Jekyll Image

In this chapter, you will use the rbenv-jekyll Docker image.  It's based on the development image but has a version of Ruby installed and a version of the Jekyll gem, which is used for creating static web sites.

## What's the point?
This chapter demonstrates the use of port forwarding for viewing web pages locally.

## Downloading the Image
* Entering the following commands in a terminal in your host system:
```
cd
cd jhsu802701
cd docker-debian-stretch # Back to the directory for using Docker images
```
* Enter the command "ls" to see the available scripts.
* Create the files for using a Docker container based on the development Docker image.
  * If you are using 64-bit Linux, enter the following command:
  ```
  sh rbenv-jekyll.sh
  ```
  * If you are using 32-bit Linux, enter the following command:
  ```
  sh 32rbenv-jekyll.sh
  ```
  * Enter the following command to enter the directory for using the development image:
  ```
  cd rbenv-jekyll
  ```
  * Enter the command "ls".  Note that this "rbenv-jekyll" directory contains scripts for using the jhsu802701/32bit-debian-stretch-rbenv-jekyll or jhsu802701/debian-stretch-rbenv-jekyll Docker image.  Again, these scripts come with important parameters already filled in for you.
  * Enter the command "ls shared".  You can see the files within the shared directory.
* Download the Jekyll Docker image and start a Docker container based on it by entering the following command:
```
sh download_new_image.sh
```
* The development Docker image will be downloaded, and a corresponding Docker container will be created. When the new Docker container is ready, you will be automatically logged in.
* When you are in the Docker container, enter the command "exit" to return to your host system.

## Time Stamp
* Enter the command "sh reset.sh".
* Note that the time stamp file has three build dates instead of two.  That's because the rbenv-jekyll Docker image is a derivative of the development Docker image, which is a derivative of the minimal Docker image.

## Removing and installing Ruby and Jekyll
