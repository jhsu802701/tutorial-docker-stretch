# Chapter 2: Using the Minimal Docker Image

In this chapter, you will download the minimal Docker image, create a Docker container from it, and learn basic Docker capabilities.  This minimal image is a basic building block for other images and does NOT come with Ruby on Rails installed.  Because the minimal Docker image  Using Ruby on Rails in Docker will be covered in later chapters.

## What's the point?
In this chapter, you will learn ways to enter a Docker container, and you will learn how to share files between the Docker container and your host environment.

## Downloading the Image
* Download the repository for using Docker images by entering the following commands in a terminal:
```
cd
cd jhsu802701
git clone https://github.com/jhsu802701/docker-debian-stretch.git
cd docker-debian-stretch
```
* Enter the command "ls".  Note that there are scripts that create the files needed for each of the available Docker images.
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
  * Enter the command "ls".  Note that this "min" directory contains scripts for using a Docker container.  These scripts come with important parameters already filled in for you.  The 32min.sh script specifies the use of the 32-bit minimal image (jhsu802701/32bit-debian-stretch-min), while the min.sh script specifies the use of the 64-bit version of this image (jhsu802701/debian-stretch-min).  There's also a shared directory within the "min" directory.
  * Enter the command "ls shared".  Files in this shared directory are accessible not only in your host environment but in your virtual Docker environment as well.  This will be demonstrated later in this chapter.
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

## Demonstration of Resume, Reset, and Download New Image
* From the min directory within the docker-debian-stretch project, enter the command "sh reset.sh".
* Note that the content of the /home/winner/timestamp.txt file is printed when you log in.  The build date is the date and time at which the Docker image you are using was built.  The unlabeled date below is the date and time at which you logged into the Docker container.
* Enter the command "exit".  Now you are back in your desktop Linux system.
* Enter the command "sh resume.sh".  You are back in the Docker container.  Note that the time stamp file has a second unlabeled date below the build date.
* Enter the command "exit".  You are in your desktop Linux system.
* Enter the command "sh resume.sh".  You are in the Docker container, and a third login date has been added to the time stamp file.
* Enter the command "exit".  You are in your desktop Linux system.
* Enter the command "sh reset.sh".  Now there is only one login date in the time stamp file.  The login dates you saw previously are gone, because you reset the Docker container to its initial state.
* Enter the command "sh download_new_image.sh".  This destroys the Docker image that you previously downloaded, downloads the newest version, and then logs you into a new Docker container based on the new image.  If your current Docker image is outdated, this script allows you to replace it with a new one, and that will be reflected in a new build date.

## Shared Directory
* When you enter the Docker container, you are automatically directed to the /home/winner/shared directory.
* Log into your minimal Docker container.  Enter the command "ls" to see the files in this shared directory.
* Enter the command "cat README-host.txt".  The fact that you can access it from the shared directory confirms that the shared directory works as expected.
* Enter the command "cat docker.txt".  This lists the name of the Docker image and Docker container you are currently using.
* Enter the command "sh info.sh".  This gives you information on your current Docker container, including the content of the time stamp file, the version of Debian Linux in use, the name of the Docker image, and the name of the Docker container, and the versions of software installed.
* The ports.txt file is not relevant here, because the ports are not set up in the Docker container based on the minimal Docker image.

## Creating Shared Directory Files
* In the /home/winner/shared directory of your Docker container, enter the following commands:
```
echo "Ruby on Racetracks" > test1.txt
cat test1.txt # The text "Ruby on Racetracks" should appear.
```
* On your desktop Linux system, go to Menu -> System Tools -> File Manager.  From your user home directory, go to jhsu802701 -> docker-debian-stretch -> min -> shared.  Open the test1.txt file, which should contain the text "Ruby on Racetracks".
* On your desktop Linux system, create the file test2.txt within the shared directory.  Open this file, give it the content "Rails Tutorial", and then save it.
* From the /home/winner/shared directory of your Docker container, enter the command "cat test2.txt".  The text "Rails Tutorial" should appear.

## Saving Shared Directory Files
* In your Docker container, enter the command "exit".  Then enter the command "sh reset.sh" to reset the Docker container.
* In the /home/winner/shared directory of your Docker container, enter the following commands:
```
echo "Ruby on Racetracks\n" > test1.txt.
cat test1.txt # The text "Ruby on Racetracks" should appear.
cat test2.txt # The text "Rails Tutorial" should appear.
```
* On your desktop Linux system, open the test1.txt and test2.txt files.  The expected content will still be in these files.
* As you can see, the shared directory files are unaffected by a Docker container reset.
* In your Docker container, enter the command "exit".  Then enter the command "sh download_new_image.sh" to destroy your current Docker image, download a new one, and enter a new Docker container.
* In the /home/winner/shared directory of your Docker container, enter the following commands:
```
echo "Ruby on Racetracks\n" > test1.txt
cat test1.txt # The text "Ruby on Racetracks" should appear.
cat test2.txt # The text "Rails Tutorial" should appear.
```
* As you can see, the shared directory files are unaffected by the process of destroying and replacing the Docker image.

## Deleting Shared Directory Files
* In your Docker container, enter the following commands:
```
rm test1.txt
ls # The test1.txt file should be gone but the test2.txt file should remain
```
* In your desktop Linux system, you should see that the test1.txt file is gone but the test2.txt file remains.
* From your desktop Linux system, delete the test2.txt file.
* In your Docker container, enter the command "ls".  The test2.txt file should now be gone.

## Purpose of the Shared Directory
* Placing the source code of your projects in the shared directory allows you to edit files with the GUI tools of your desktop Linux while processing and testing them with the software tools in your Docker container.
* When you use a Docker container with pre-installed Ruby on Rails, you can test your Rails app in your Docker container and use the Geany editor (a GUI tool) to view and edit your source code files.  You don't need any GUI tools in your Docker container, and you don't need Ruby on Rails in your desktop Linux setup.
