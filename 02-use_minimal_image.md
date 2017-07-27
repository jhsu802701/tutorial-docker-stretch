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
* 
