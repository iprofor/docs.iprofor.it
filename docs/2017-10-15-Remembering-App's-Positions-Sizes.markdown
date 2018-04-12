---
layout: post
title:  "Remembering Application's Positions Sizes on Ubuntu 16.04"
date:   2017-10-15
---

In order to launch an application on a separate workspace, the following packages should be installed

##### On Ubuntu
`apt -y install compizconfig-settings-manager`

* Launch __compizconfig-settings-manager__
* Click on __Windows Manager__
* Click on __Place Windows__
* Use these settings:
  - Workarounds _Unticked_
  - Placement Mode _Place across all outputs_
  - The Placement Mode _Smart_ is the key for remembering your desired position.
  - Please keep in mind that some applications are programmed to override your system's perferred settings.
