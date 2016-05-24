---
title: How to install Node.js in AWS
date: 2016-05-24 01:07:15
tags:
- AWS
- Node.js
---
___

Make sure you have an EC2 instance running before this step.

### Connect to your Amazon EC2 Linux box

On windows, use Putty to connect to Amazon EC2 Linux box.

On Linux/Mac, use _ssh_ command to connect.

``` bash
$ sudo chmod 400 <your key file>
$ sudo ssh -i <your key file> ec2-user@<your public DNS>
```

### Switch to the home folder and update the Amazon system

``` bash
$ cd /home/ec2-user/
$ sudo yum update
```

### Install GCC++, Make, openssl-devel, and git

``` bash
$ sudo yum install gcc-c++ make openssl-devel git
```

### Download Node.js from Github

``` bash
$ git clone git://github.com/nodejs/node.git
$ cd node
```

### Switch to LTS version, click [HERE](https://nodejs.org/en/) to check current LTS version.

``` bash
$ git checkout v4.4.4
```

### Compile Node.js, take around 10 minutes.

``` bash
$ ./configure
$ make
$ sudo make install
```

### Install NPM

Before installing any node modules, you need to add path where those modules should get installed. To do so, you need to edit sudoers file.

```bash
$ sudo su
$ vi /etc/sudoers

# once VI is opened, find this line.
# Defaults    secure_path = /sbin:/bin:/usr/sbin:/usr/bin
# press 'i' key to go in insert mode and at the end of this line add following.
# :/usr/local/bin
# In order to save your changes, press ESC and type 'wq!' and hit ENTER to exit.

$ exit
$ cd /home/ec2-user/
$ git clone https://github.com/isaacs/npm.git
$ cd npm
$ sudo make install
```