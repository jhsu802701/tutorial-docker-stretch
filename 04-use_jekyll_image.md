# Chapter 4: Using the Jekyll Image

In this chapter, you will use the jekyll-general Docker image.  It's based on the development image but has a version of Ruby installed and a version of the Jekyll gem, which is used for creating static web sites.

## Topics
* Viewing local web pages on your desktop Linux system
* Using Geany in the host system to edit files in the shared directory

## Downloading the Image
* Entering the following commands in a terminal in your desktop Linux system:
```
cd
cd rubyonracetracks
cd docker-debian-stretch # Back to the directory for using Docker images
```
* Enter the command "ls" to see the available scripts.
* Create the files for using a Docker container based on the development Docker image.
  * If you are using 64-bit Linux, enter the following command:
  ```
  sh jekyll-general.sh
  ```
  * If you are using 32-bit Linux, enter the following command:
  ```
  sh jekyll-general.sh
  ```
  * When prompted for an offset of the port number, enter "0".
  * Enter the following command to enter the directory for using the development image:
  ```
  cd jekyll-general
  ```
  * Enter the command "ls".  Note that this "jekyll-general" directory contains scripts for using the rubyonracetracks/32bit-debian-stretch-jekyll-general or rubyonracetracks/debian-stretch-jekyll-general Docker image.  Again, these scripts come with important parameters already filled in for you.
  * Enter the command "ls shared".  You can see the files within the shared directory.
* Download the Jekyll Docker image and start a Docker container based on it by entering the following command:
```
sh download_new_image.sh
```
* The Jekyll Docker image will be downloaded, and a corresponding Docker container will be created. When the new Docker container is ready, you will be automatically logged in.
* When you are in the Docker container, enter the command "exit" to return to your desktop Linux system.

## Time Stamp
* Enter the command "sh reset.sh".
* Note that the time stamp file has three build dates instead of two.  That's because the jekyll-general Docker image is a derivative of the development Docker image, which is a derivative of the minimal Docker image.

## Information
* Enter the command "sh info.sh".  You'll see that a version of Ruby is installed, and a version of Jekyll is installed.
* Note the port forwarding information, which is stored in the ports.txt file in the shared directory.  You'll see that port 4000 in Docker corresponds to port 4000 in the Docker container's host system.

## Removing and Restoring Ruby and Jekyll
* Enter the command "rbenv versions".  You'll see the system version of Ruby and one additional numbered version pre-installed with rbenv (the Ruby version manager).
* Enter the command "ruby -v".  This shows you the version of Ruby currently in use.
* Enter the command "jekyll -v".  This shows you the version of Jekyll currently in use.
* Enter the command "rm -rf /home/winner/.rbenv".  This removes rbenv, all versions of Ruby installed with rbenv, and Jekyll (which was installed within Ruby).
* Enter the command "rbenv versions".  You'll get the error message "command not found".
* Enter the command "ruby -v".  You'll see an old version of Ruby in use.  This is the Ruby version that was automatically installed during the process of creating the development Docker image.
* Enter the command "jekyll -v".  You'll get the error message "No such file or directory".
* Enter the command "exit".
* Enter the command "sh resume.sh".
* Enter the command "rbenv versions".  Again, you'll get the error message "command not found".
* Enter the command "ruby -v".  Again, you'll see an old version of Ruby in use.
* Enter the command "jekyll -v".  You'll get the error message "command not found".
* Enter the command "exit".
* Enter the command "sh reset.sh".
* Enter the command "rbenv versions".  Now you'll see the original (newer) version of Ruby for this Docker container.
* Enter the command "ruby -v".  Now you'll see the original (newer) version of Ruby for this Docker container.
* Enter the command "jekyll -v".  Now you'll see that Jekyll is back.

## Starting and Viewing the Jekyll Test App
* Enter the command "sh test-jekyll.sh".  This script automatically builds a quick test site.  This runs the info.sh script, generates a new Jekyll project, and starts up the local server in your Docker container.
* In the web browser in your desktop Linux, open the URL "localhost:4000".  You should now see your new Jekyll project.

## Editing the Jekyll Test App
* Your Jekyll test app is in the my-awesome-site directory.  Within this directory is the file index.md, the main page of this Jekyll app.
* In your desktop Linux system, open the index.md file with the Geany editor.
* At the end of the index.md file, add the following code:
```
There's Ruby on Racetracks, and there's Not Exactly.  Make sure you choose the correct one.
```
* In the Docker container, enter Ctrl-c to stop the Jekyll server.  You should be back in the shared directory.
* Enter the command "cd my-awesome-site && jekyll serve --host 0.0.0.0".
* In the web browser in your desktop Linux, open the URL "localhost:4000".  You should now see your Jekyll web page again, but you'll see the message that you just added to the index.md file added to the page.
* In the Docker container, enter Ctrl-c to stop the Jekyll server.
* Enter the command "exit".
