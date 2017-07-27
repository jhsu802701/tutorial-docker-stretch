Chapter 3: Using the Development Image

In this chapter, you will download the development Docker image and learn more of the basic capabilities of Docker.  This development image is a derivative of the minimal image used in the previous chapter but has basic software development tools added, such as Git, Heroku, Node Version Manager, Node.js, Python, and rbenv.

## Downloading the Image
* Download the repository for using Docker images by entering the following commands in a terminal:
```
cd
cd jhsu802701
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
  * Enter the command "ls".  Note that this "dev" directory contains scripts for using the jhsu802701/32bit-debian-stretch-dev or jhsu802701/debian-stretch-dev Docker image.  Again, these scripts come with important parameters already filled in for you.
  * Enter the command "ls shared".  You can see the files within the shared directory.
* Download the development Docker image and start a Docker container based on it by entering the following command:
```
sh download_new_image.sh
```
* The development Docker image will be downloaded, and a corresponding Docker container will be created. When the new Docker container is ready, you will be automatically logged in.
* When you are in the Docker container, enter the command "exit" to return to your desktop Linux system.

