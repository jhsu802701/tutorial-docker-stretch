# Chapter 5: Using the General Purpose Ruby on Rails Image

In this chapter and the rest of the chapters in this tutorial, you will use the rbenv-general Docker image.  It's based on the development image but includes Ruby, Rails, and other selected Ruby gems.

## Downloading the Image
* Entering the following commands in a terminal in your desktop Linux system:
```
cd
cd jhsu802701
cd docker-debian-stretch # Back to the directory for using Docker images
```
* Enter the command "ls" to see the available scripts.
* Create the files for using a Docker container based on the development Docker image.
  * If you are using 64-bit Linux, enter the following command:
  ```
  sh rbenv-general.sh
  ```
  * If you are using 32-bit Linux, enter the following command:
  ```
  sh 32rbenv-general.sh
  ```
  * Enter the following command to enter the directory for using the development image:
  ```
  cd rbenv-general
  ```
  * You will be asked about your desired offset for the port numbers.  Enter "0".
  * Enter the command "ls".  Note that this "rbenv-general" directory contains scripts for using the jhsu802701/32bit-debian-stretch-rbenv-general or jhsu802701/debian-stretch-rbenv-general Docker image.  Again, these scripts come with important parameters already filled in for you.
  * Enter the command "ls shared".  You can see the files within the shared directory.
* Download the rbenv-general Docker image and start a Docker container based on it by entering the following command:
```
sh download_new_image.sh
```
* The General Purpose rbenv-general Docker image will be downloaded, and a corresponding Docker container will be created. When the new Docker container is ready, you will be automatically logged in.
* When you are in the Docker container, enter the command "exit" to return to your desktop Linux system.

## Time Stamp
* Enter the command "sh reset.sh".
* Note that the time stamp file has three build dates instead of two.  That's because the rbenv-jekyll Docker image is a derivative of the development Docker image, which is a derivative of the minimal Docker image.

## Information
* Enter the command "sh info.sh".  You'll see that a version of Ruby is installed, and versions of Rails are installed.
* Note the port forwarding information, which is stored in the ports.txt file in the shared directory.  You'll see that port 3000 in Docker corresponds to port 3000 in the Docker container's host system.

## Removing and Restoring Ruby on Rails
* Enter the command "rbenv versions".  You'll see the system version of Ruby and one additional numbered version pre-installed with rbenv (the Ruby version manager).
* Enter the command "ruby -v".  This shows you the version of Ruby currently in use.
* Enter the command "rails -v".  This shows you the version of Rails currently in use.
* Enter the command "rm -rf /home/winner/.rbenv".  This removes rbenv, all versions of Ruby installed with rbenv, and Rails (which was installed within Ruby).
* Enter the command "rbenv versions".  You'll get the error message "command not found".
* Enter the command "ruby -v".  You'll see an old version of Ruby in use.  This is the Ruby version that was automatically installed during the process of creating the development Docker image.
* Enter the command "rails -v".  You'll get the error message "No such file or directory".
* Enter the command "exit".
* Enter the command "sh resume.sh".
* Enter the command "rbenv versions".  Again, you'll get the error message "command not found".
* Enter the command "ruby -v".  Again, you'll see an old version of Ruby in use.
* Enter the command "rails -v".  You'll get the error message "command not found".
* Enter the command "exit".
* Enter the command "sh reset.sh".
* Enter the command "rbenv versions".  Now you'll see the original (newer) version of Ruby for this Docker container.
* Enter the command "ruby -v".  Now you'll see the original (newer) version of Ruby for this Docker container.
* Enter the command "rails -v".  Now you'll see that Rails is back.
* Enter the command "exit".
* If you had deleted Ruby on Rails from a host system, it would take you hours to fully reinstall it.
