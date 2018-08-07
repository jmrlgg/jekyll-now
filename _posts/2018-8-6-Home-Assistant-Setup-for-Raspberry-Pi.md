---
title: Raspberry Pi Home Assistant Install
---

Raspberry Pi HomeAssistant Install and Setup
============================================

Raspberry Pi Home Assistant Overview
------------------------------------

> Make sure you have your Raspberry Pi setup with SSH enabled, and running on the proper power supply. If not Check out our Raspberry Pi Installation.

We are going to install on a virtual environment, which will have minimal overhead. Firstly, you’ll need Python 3.5.3 or later installed, which is fine if you have Raspbian Stretch.

Raspberry Pi Home Assistant Setup
---------------------------------

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ssh
$ ssh <pi@raspberrypi.local>  
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ssh
$ sudo apt-get update  
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ssh
$ sudo apt-get upgrade -y  
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Raspberry Pi Installation of Dependencies
-----------------------------------------

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ssh
$ sudo apt-get install python3 python3-venv python3-pip
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Now we will add an account for Home Assistant called `homeassistant`. This will only be used for running Home Assistant so we will use the extra arugments of `-rm` to create a system account and home directory. `-G dialout,gpio`, adds the user to `dialout` and the `gpio` group. Zigbee and Z-Wave controllers need dialout, and gpio is used for the GPIO Pins on the Raspberry Pi.

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ssh
$ sudo useradd -rm homeassistant -G dialout,gpio
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Now we will create a directory on the Raspberry Pi to install Home Assistant
into. Also we need to change the owner to `homeassistant`.

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ssh
$ cd /srv
$ sudo mkdir homeassistant
$ sudo chown homeassistant:homeassistant homeassistant
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Now we need to create and change to our virtual enviornment for Home Assistant.
This will need to be done in our `homeassistant` account.

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ssh
$ sudo -u homeassistant -H -s
$ cd /srv/homeassistant
$ python3 -m venv .
$ source bin/activate
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

After you have activated your `homeassistant` virtual enviornment, we will need to run a command to install a required python package.

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ssh
(homeassistant) homeassistant@raspberrypi:/srv/homeassistant $ python3 -m pip install wheel
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Once you have installed the required python package it is now time to install Home Assistant!

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ssh
(homeassistant) homeassistant@raspberrypi:/srv/homeassistant $ pip3 install homeassistant
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Now to our final step to Start Home Assistant for the first time. This will complete the installation, create the .homeassistant configuration directory in the /home/homeassistant directory and install any basic dependencies.

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~bash
(homeassistant) $ hass
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

You can now reach your installation on your Raspberry Pi over the web interface on http://ipaddress:8123.

You can find your ip address using this command

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~bash
$ ipconfig
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~



>   When you run the hass command for the first time, it will download, install
>   and cache the necessary libraries/dependencies. This procedure may take
>   anywhere between 5 to 10 minutes. During that time, you may get “site cannot
>   be reached” error when accessing the web interface. This will only happen
>   for the first time, and subsequent restarts will be much faster.
