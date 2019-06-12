---
title: Working With WordPress
date: 2019-06-11T23:41:00.131Z
image: /images/wordpress-icon.png
tags:
  - '#WordPress'
  - '#Hacklafayette'
published: false
---
<br>
<br>

&emsp; Have you ever wanted to setup a WordPress site, but don't want to use WordPress.com or an expensive paid host ? Well you have come to the right place. In this article I will go over how to setup a WordPress site on Google Cloud. <br>

###Step one, setup Google Cloud account
<br>
&emsp;Before we go through the steps of getting Google Cloud going you need to have access to a Google account such as gmail.Once you have that set and ready to login goto [Google Compute](https://cloud.google.com/compute/). Once there click **Go To Console** and click **Create Instance**. While setting it up choose cpu type _micro_ unless you think you will get a lot of traffic from the start. This can always be changed later, but the higher you go the more cost involved.  With the micro cpu it not cost you a whole lot to maintain, the only real cost is a static IP which you will need to host a domain name. The next step will be to choose an OS or choose to upload a premade VM. For the OS I recommend Ubuntu 18.04 or higher if you choose to go unstable. These are minimal installs and you will have to update and install the tools you need as we go, or you can choose to add back in the core utilities once logged into the console. I'm including some more resources at the end of the article for references if you did not get anything I explained in this section. 
<br>

###Lets get gcloud on your local machine
<br>
&emsp;This part of the process can be skipped if you wish to use the browser console.  However I recommend it for ease of access and also helps set yourself up for future projects to deploy off your local machine. <br>
&emsp; Most developers use one of the two recommended OS paths to do this is [Fedora](https://cloud.google.com/sdk/docs/quickstart-redhat-centos) and [Ubuntu](https://cloud.google.com/sdk/docs/quickstart-debian-ubuntu), windows and macOS is also available if you live that life. There is also just a [Linux](https://cloud.google.com/sdk/docs/quickstart-linux) general install path if you use other flavors of Linux or want an shell script.  
