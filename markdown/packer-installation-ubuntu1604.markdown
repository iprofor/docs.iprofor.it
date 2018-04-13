---
layout: post
title:  "How to Install packer.io on Ubuntu 16.04"
date:   2018-04-04
image: packer.png
---

This short tutorial is going to cover how to install Packer on Ubuntu 16.04 so that you can get started with exploring many great features of Packer.  

#### Download Packer
`curl -L https://releases.hashicorp.com/packer/1.2.2/packer_1.2.2_linux_amd64.zip > packer.zip`

#### Extract Packer to the right system location
`sudo unzip packer.zip -d /usr/local/packer`

#### Add Packer to the PATH
`echo "export PATH="$PATH:/usr/local/packer"" >> /etc/environment`
`source /etc/environment`

#### Verify the installation
`packer -v`

#### Bonus
As a bonus, I made a bash [script](https://gist.githubusercontent.com/iprofor/e712aad50b274a78c98b9b392e587e32/raw/28d8cdf4bf172993f711df0ecdede4b7f5cf2904/install-packer-ubuntu1604.sh). Remember it should be executed as root.  

<script src="https://gist.github.com/iprofor/e712aad50b274a78c98b9b392e587e32.js"></script>  

Inspired from [here](https://howtoprogram.xyz/2016/11/29/install-packer-ubuntu-16-04-1-lts-xenial-xerus/)
