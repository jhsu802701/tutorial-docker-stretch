# Chapter 1: Installing Docker

## Procedure
* Open a new terminal window.  In SparkyLinux, go to Menu -> System Tools -> LXTerminal.
* Install Git, the standard version control system.  In the terminal window, enter the following command:
```
sudo apt-get install -y git
```
* To install Docker in a 32-bit Linux system, enter the following commands:
```
mkdir jhsu802701
cd jhsu802701
git clone https://github.com/jhsu802701/docker-32bit-debian-stretch-install.git
cd docker-32bit-debian-stretch-install
sh main.sh
cd
cd jhsu802701
rm -rf docker-32bit-debian-stretch-install
```
* To install Docker in a 64-bit Linux system, enter the following commands:
```
mkdir jhsu802701
cd jhsu802701
git clone https://github.com/jhsu802701/docker-64bit-debian-stretch-install.git
cd docker-64bit-debian-stretch-install
sh main.sh
cd
cd jhsu802701
rm -rf docker-64bit-debian-stretch-install
```
* Docker will be installed in a few minutes.  In addition, other development software that you will need later is also installed, including KeePassX (for generating, encrypting, and storing passwords), Geany (code editor), SearchMonkey (search engine for local files), SQLite database browser (for viewing the SQLite database), and PG Admin (for viewing the PostgreSQL database).
* Don't worry if the Docker installation process results in the message "Are you trying to connect to a TLS-enabled daemon without TLS?"  This is normal.
