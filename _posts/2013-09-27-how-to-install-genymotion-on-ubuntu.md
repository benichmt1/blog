---
layout: post
title: "how to install genymotion on ubuntu"
description: "how to install genymotion on ubuntu"
category: ubuntu
tags: [android,ubuntu]
---
{% include JB/setup %}

##Overview
Genymotion is a complete set of tools that provides a virtual environment for Android. It can be very useful for developers, testers, salesman or even gamers.

It is available for most operating systems: Windows, Linux and MacOS X. It is as simple to install as powerful to use:  
Follow the simple install process, choose one of our Android virtual devices, start it, and enjoy it!
<!-- more -->

##Features
###Android as its best
* OpenGL acceleration to achieve the best 3D performance
* Install application from Google Play
* Enable full screen option and improve your experience

###Fully controllable
* Start multiple virtual device at the same time
* Manage sensors:  
    * Battery level / status        
    * GPS       
    * Rotation       
    * Camera       
* Directly command virtual devices sensors with Genymotion shell
* Fully compatible with ADB. You can control your virtual device from the host  

###Manage your devices
* Easy to install
* Compatible with Microsoft Windows 32/64 bits, Mac OSX 10.5+ and Linux 32/64 bits
* Configure virtual devices:         
    * Screen resolution       
    * Memory quantity       
    * CPU unit quantity       
* Download and deploy easily the lastests Genymotion Virtual Device

###Start your virtual devices from Eclipse
* Test your applications with Genymotion

##Requirements
###Operating System requirements
You need one of the following system:

* Microsoft Windows XP SP3 (32 or 64 bits)
* Microsoft Windows Vista (32 or 64 bits)
* Microsoft Windows 7 (32 or 64 bits)
* Linux Ubuntu 12.04
* Linux Ubuntu 12.10
* Linux Debian Wheezy
* Mac OS X 10.6

###System requirements
* OpenGL 2.0 capable graphic card, with an up-to-date driver
* VT-x or AMD-V capable CPU, enabled in BIOS settings
* At least 2GB of RAM memory
* At least 100 MB of free space on Hard Drive for Genymotion installation)  
A minimum of 2GB of free space is required to deploy each Genymotion virtual devices. They might need more than 8 GB depending on your usage of the virtual devices and the applications you have installed.
* Internet connection (installation and updates)
* Screen resolution greater than 1024 x 768 pixels

###Application requirements
* Oracle VirtualBox >= 4.1 (greater is better)

##Installation
###Register  
1.Go to Genymotion register page  
2.In signup form, fill the fields with your personnal informations  
3.Click on Sign up button  
4.You'll receive a validation E-mail. Click on the validation link to finish  
5.You'll receive another E-mail, indicating that your registration is now complete  

###Download and Install Oracle VirtualBox
If you don't already have VirtualBox installed, read the following section.

* Windows  
The simpliest way to install VirtualBox is to download the Genymotion package that contains VirtualBox installer here

* MacOS X  
Go to VirtualBox download page and get the MacOS X dmg file. Open the dmg file and follow the installation steps. When finished, reboot.

* Linux  
Check your repositories: almost every GNU/Linux have a package installer for VirtualBox. If not, or if you need to install a specific version, go to VirtualBox download page

###Download Genymotion
1.Go to official Genymotion download page  
2.Select the package corresponding to your system and download it  

###Install Genymotion
Depending of your system, follow the install process:

* Windows  
   1.Double click on msi installer   
   2.Choose the installer language (the Genymotion language depends of your system     language) and click on Next button  
   3.Click on Next button again  
   4.Change the path if needed (the default path is C:\Program   Files\Genymobile\Genymotion) then click on Next button  
   5.Click on Next button again  
   6.Choose weither or not create desktop icon. Then click on Next button  
   7.Click on Install button  
   8.Click on Finish button 
 
* MacOS X     
   1.Open the dmg installer
   2.Move Genymotion and Genymotion shell to application directory
   
* Linux  
In a terminal:

                  chmod +x {InstallerPath}/genymotion.bin
                  [InstallerPath]/genymotion.bin
                

##Quick start
1、Run Genymotion    
     *  Windows  
Click on the icon on your desktop

     *  MacOS   
Click on the icon from the Application directory

     *  Linux    
Launch {InstallationPath}/genymotion

2、The main window appears:  
![Genymotion main window](https://cloud.genymotion.com/static/images/doc/screenshots/genymotion-main-window.png)


3、And immediately, a pop-up appears and invites you to add your first virtual device:            
![Genymotion main window add device](https://cloud.genymotion.com/static/images/doc/screenshots/genymotion-no-device-add.png)

4、Click on Yes button.  
The creation window appears:
![Genymotion not connected](https://cloud.genymotion.com/static/images/doc/screenshots/genymotion-new-no-connected.png)
      
5、Click on Connect button  
Fill with your username or your email address, then fill the password field and click on Connect button

![Genymotion connection](https://cloud.genymotion.com/static/images/doc/screenshots/genymotion-connect.png)
      
6、When connected, you can see all the available virtual device:  

![Genymotion connection](https://cloud.genymotion.com/static/images/doc/screenshots/genymotion-connected.png)

7、Select a virtual device (Nexus 7 - 4.2.2 - with google apps in the example) in the bottom list and click on add button:  

![Genymotion new resume](https://cloud.genymotion.com/static/images/doc/screenshots/genymotion-new-resume.png)
    
8、Click on next button  

![Genymotion finished download](https://cloud.genymotion.com/static/images/doc/screenshots/genymotion-new-download-finished.png)

9、Choose a name for your new virtual device, and then click on Create.  

![Genymotion deployment](https://cloud.genymotion.com/static/images/doc/screenshots/genymotion-new-deploy.png)

10、Click on close to return to the main window  

![Genymotion deployment](https://cloud.genymotion.com/static/images/doc/screenshots/genymotion-device-created.png)

11、Click on play then discover  

![Genymotion main window](https://cloud.genymotion.com/static/images/doc/screenshots/genymotion-player-ready.png)

##Reference
* User Guide  
[https://cloud.genymotion.com/page/doc/](https://cloud.genymotion.com/page/doc/)
