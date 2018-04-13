---
layout: post
title:  "How to Install Ruby on Ubuntu 16.04"
date:   2017-11-02
image: ruby.jpg
---

#### Prerequisites
In order to install Ruby on the host machine, one should already have _Node.js_ environment installed.  

Here are the steps on how to install [_Node.js_]({{ site.baseurl }}{% link _posts/2017-09-13-How-To-Install-Nodejs-On-Ubuntu-1604.markdown %})  


#### Adding the source repository
In order to install Ruby on the system, one should add source repository, authenticate it and update/upgrade the system  

`curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add - && echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list && apt -y update && apt -y upgrade && apt -y dist-upgrade && apt -y autoremove`  

#### Installation
Then to actually install needed packages  
`apt -y install git-core curl zlib1g-dev build-essential libssl-dev libreadline-dev libyaml-dev libsqlite3-dev sqlite3 libxml2-dev libxslt1-dev libcurl4-openssl-dev python-software-properties libffi-dev nodejs yarn ruby ruby-dev make build-essential`

Inspired from [here](https://gorails.com/setup/ubuntu/16.04)
