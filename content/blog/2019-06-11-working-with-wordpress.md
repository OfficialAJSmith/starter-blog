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
&emsp;Before we go through the steps of getting Google Cloud going you need to have access to a Google account such as gmail.Once you have that set and ready to login goto [Google Compute](https://cloud.google.com/compute/). Once there click **Go To Console** and click **Create Instance**. While setting it up choose cpu type _micro_ unless you think you will get a lot of traffic from the start. This can always be changed later, but the higher you go the more cost involved.  With the micro cpu it will not cost you a whole lot to maintain, the only real cost is a static IP which you will need to use a domain name. The next step will be to choose an OS or choose to upload a premade VM. For the OS I recommend Ubuntu 18.04 or higher if you choose to go unstable. These are minimal installs and you will have to update and install the tools you need as we go, or you can choose to add back in the core utilities once logged into the console. I'm including some more resources at the end of the article for references if you did not get anything I explained in this section. 
<br>

###Lets get gcloud on your local machine
<br>
&emsp;This part of the process can be skipped if you wish to use the browser console.  However I recommend it for ease of access and also helps set yourself up for future projects to deploy off your local machine. <br>
&emsp; Most developers use one of the two recommended OS paths to do this is [Red Hat / Centos](https://cloud.google.com/sdk/docs/quickstart-redhat-centos) and [Debian / Ubuntu](https://cloud.google.com/sdk/docs/quickstart-debian-ubuntu), windows and macOS is also available if you live that life. There is also just a [Linux](https://cloud.google.com/sdk/docs/quickstart-linux) general install path if you use other flavors of Linux or want an shell script. My personal flavor is Fedora which can use any of the Red Hat RPM packages. So the install method I choose was with yum and you have to add the repo date before using it. Use the following command to launch and editor:
```
sudo tee -a /etc/yum.repos.d/google-cloud-sdk.repo << EOM
```
Once you have done this it will launch a prompt with ">".
```
Copy and paste the following into that section and press enter:

[google-cloud-sdk]
name=Google Cloud SDK
baseurl=https://packages.cloud.google.com/yum/repos/cloud-sdk-el7-x86_64
enabled=1
gpgcheck=1
repo_gpgcheck=1
gpgkey=https://packages.cloud.google.com/yum/doc/yum-key.gpg
       https://packages.cloud.google.com/yum/doc/rpm-package-key.gpg
EOM
```
If you have done this correctly you should find yourself back at the bash console. Now you can use the following command to fetch the sdk.
```
yum install google-cloud-sdk
```
You should note that this installs the minimum files required to use Google Cloud SDK and if you want app engine support or other file support you will have to install them manually. We will not be covering this part here as it is not needed for this project. If you wish to use these tools visit Google Cloud Developers page for more details. Now that we have gcloud setup for use with our local machine we can setup a webserver.  
<br>
##Swap File setup
&emsp;Since we are using only 512mb of ram on the this compute engine it is recommended that you install a 1gb swap file to help with performance. Here are the steps to do that. First you need to allocate some space:
```
sudo fallocate -l 1G /swapfile
```
Now you can use dd to move the allocated space. Be Careful and only type what I have provided unless your positive you know what you're doing. DD can damage your file system:
```
sudo dd if=/dev/zero of=/swapfile bs=1024 count=1048576
```
Once that is done, it may take a few minutes so please wait until it's done. After this we can change access to the swapfile so that only root can access it, we will use chmod to do so. 
```
sudo chmod 600 /swapfile
```
Root access is now setup and we can use mkswap to create the file need for swap and fstab. 
```
sudo mkswap /swapfile
```
You have now created a file to link with swap use the following command to turn it on:
```
 sudo swapon /swapfile
```
Be sure to add this to your fstab config to load it in the even you need to restart or your compute engine. below is the command and information to paste into the fstab config.
```
sudo nano /etc/fstab

#paste this in the fstab file and save it.
/swapfile swap swap defaults 0 0
```
###Web Server (Lamp) 
<br>
&emsp;There is a few methods you can install a LAMP server with a single command or you can choose to install each component individual if you need specific versions or a container setup. The version I choose to do was with apt-get which handles all the dependencies needed to make the basic stack. After this you will have to add a few additional items that we will go over. Use the following command to get started:
```
sudo apt-get install lamp-server^
```
If your install does not go well do not remove lamp-server with the caret "^" because it will remove all libraries attached to it and break your system. Also don't forget it when installing as it will not include everything needed. I mentioned a few extra items that need installed to finish out the lamp stack setup. Use the bit below to install these.
```
sudo apt install php-curl php-gd php-mbstring php-xml php-xmlrpc
```
###Apache config 
&emsp;In this second we will setup the apache config so that we can point our web address to the proper ip and apache conf files. 



  

