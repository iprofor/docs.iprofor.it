---
layout: post
title:  "First Steps with Jekyll on Ubuntu 16.04"
date:   2017-11-20
image: jekyll.png
---

### Prerequisites
Innnn order to install Jekyll on the host machine, one should already have _Node.js_ and _Ruby_ environments installed.  

Here are the steps to firstly install [_Node.js_]({{ site.baseurl }}{% link _posts/2017-09-13-How-To-Install-Nodejs-On-Ubuntu-1604.markdown %}) and then [_Ruby_]({{ site.baseurl }}{% link _posts/2017-11-02-How-To-Install-Ruby-On-Ubuntu-1604.markdown %})

#### Installation
Installing the jekyl and the bundler  
`sudo gem install bundler jekyll`

To see the installed version, run the following command  
`jekyll -v`

#### Plugins
Installing additional needed plug-ins  
`sudo gem install jekyll-paginate jekyll-gist`

#### Debuging a site  
cd into the directory  
`jekyll doctor`

#### Creating a standard blank a site
`jekyll new my-awesome-site`

#### Publishing a site
cd into the directory  
`jekyll serve`  
or  
`bundle exec jekyll serve`  

or by indicating the host's IP, e.g. _10.10.10.10_  
`jekyll serve -H 10.10.10.10`  
or  
`bundle exec jekyll serve -H 10.10.10.10`  

Inspired from [here](https://www.digitalocean.com/community/tutorials/how-to-set-up-a-jekyll-development-site-on-ubuntu-16-04)
