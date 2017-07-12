# Chapter 3: Entering a Docker Container

In this chapter, you will learn about three ways to enter a Docker container.  In the previous chapter, you run the rbenv-general.sh script or the 32rbenv-general.sh script within the docker-debian-stretch repository to generate additional scripts for working with one of my rbenv-general Docker scripts.  These scripts are within the rbenv-general directory within the docker-debian-stretch repository.

## Scripts For Entering a Docker Container
* reset.sh: This is the script you use to destroy your current Docker container and start up a brand new Docker container based on your local copy of the Docker image.  In other words, you reset your Docker container's environment to the initial conditions.  It's analogous to reinstalling the OS on your computer.  The difference is that resetting your Docker container takes no more than a few seconds.  (NOTE: If the expected Docker image is not present, it will be automatically downloaded for you, as if you ran the download_new_image.sh script instead.)
* resume.sh: This is the script you use to return to your current Docker container under the same conditions that were in place when you last exited it.  It's analogous to booting up your computer after you turned it off.  The difference is that resuming your Docker container takes no more than a few seconds, because you bypass the 
* download_new_image.sh: This is the script you used in the previous chapter to download the Docker image from [Docker Hub](https://hub.docker.com/) and enter the resulting Docker container.  When you run this script after you already created a Docker container from this image, you not only destroy the local container, but you also destroy your local copy of the Docker image and download a new one from [Docker Hub](https://hub.docker.com/).  If your current local copy of the Docker image is outdated, running this script replaces it with the latest image.

## Using reset.sh
* At the end of the previous chapter, you entered the command "exit" inside Docker in order to exit the Docker container you created from the downloaded Docker image.  You are back in the rbenv-general directory within the docker-debian-stretch repository.
* Enter the following command to reset the Docker container:
```
sh reset.sh
```
* Note that every time you start up the Docker container, the contents of the file /home/winner/timestamp.txt are printed out.  The 
