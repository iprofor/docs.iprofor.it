---
layout: post
title:  "How to Set Up and Use LXD 2.0.x on Ubuntu 16.04"
date:   2018-03-15
image: lxd-containers.png
---

A Linux container is a grouping of processes that is isolated from the rest of the system through the use of Linux kernel security features, such as namespaces and control groups. It's a construct similar to a virtual machine, but it's much more light-weight; you don't have the overhead of running an additional kernel or simulating the hardware. This means you can easily create multiple containers on the same server.

LXD lets you create and manage these containers. LXD provides a hypervisor service to manage the entire life cycle of containers. In this tutorial, you'll configure LXD and use it to run Nginx in a container. You'll then route traffic to the container in order to make the web site accessible from the Internet.


`sudo apt -y install lxd`

Log in to the server using the non-root user account. Then add your user to the lxd group so you can use it to perform all container management tasks:

`sudo usermod --append --groups lxd crt`

**For server**  
Log out of the server and log back in again so that your new SSH session will be updated with the new group membership. Once you're logged in, you can start configuring LXD.

**For Desktop**  
The new group will be effective at the next login session, to apply it to the current shell, run

`newgrp lxd`


Now configure the storage backend. The recommended storage backend for LXD is the ZFS filesystem, stored either in a preallocated file or by using Block Storage. To use ZFS support in LXD, update your package list and install the zfsutils-linux package:

`sudo apt -y update`

`sudo apt -y install zfsutils-linux`

You can now configure LXD. Start the LXD initialization process with the lxd init command:

`sudo lxd init`

    Enter (yes)
    Enter (zfs)
    Enter (yes)
    Enter (lxd)
    Enter (no)
    8
    yes
    Enter (all)
    Enter (8443)
    Password
    Enter (yes)
    Enter (yes)
    Enter (lxdbr0)
    Enter (yes)
    Enter (ok)
    10.10.90.1
    24
    10.10.90.2
    10.10.90.254
    250
    Enter (yes)
    Enter (no)

`lxc list`


### Images
Inspired from [here](https://linuxcontainers.org/lxd/getting-started-cli/)

List of images from [here](https://uk.images.linuxcontainers.org/)

lxc launch images:centos/7/amd64 centos7-test

**Using the built-in image remotes**
LXD comes with 3 default remotes providing images:

- ubuntu: (for stable Ubuntu images)
- ubuntu-daily: (for daily Ubuntu images)
- images: (for a bunch of other distros)

To start a container from them, simply do:

`lxc launch ubuntu:14.04 my-ubuntu`  
`lxc launch ubuntu-daily:16.04 my-ubuntu-dev`  
`lxc launch images:centos/6/amd64 my-centos`  


If you need to connect to the container as root, use the command

`lxc exec centos7-test -- /bin/bash`

If you need to connect to the ubuntu/debian container as user, use the command

`lxc exec webserver -- sudo --login --user ubuntu`


**Container's rootfs on the host OS**  
`cd /var/lib/lxd/containers`  

Inspired from [here](https://www.digitalocean.com/community/tutorials/how-to-set-up-and-use-lxd-on-ubuntu-16-04) and [here](https://tutorials.ubuntu.com/tutorial/tutorial-setting-up-lxd-1604#0)
