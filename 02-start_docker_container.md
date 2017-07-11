# Chapter 2: Starting the Docker Container

## Procedure
* Download the repository for using Docker images by entering the following commands in a terminal:
```
cd
cd jhsu802701
git clone https://github.com/jhsu802701/docker-debian-stretch.git
cd docker-debian-stretch
```
* Create the files for using the rbenv-general Docker container.
  * If you are using 64-bit Linux, enter the following command:
  ```
  sh rbenv-general.sh
  ```
  * If you are using 32-bit Linux, enter the following command:
  ```
  sh 32rbenv-general.sh
  ```
* Download the rbenv-general Docker container by entering the following commands:
```
cd rbenv-general
sh download_new_image.sh
```
* The rbenv-general Docker image will be downloaded, and a corresponding Docker container will be created. When the new Docker container is ready, you will be automatically logged in.
* When you are in the Docker container, enter the command "exit" to return to your desktop Linux system.
