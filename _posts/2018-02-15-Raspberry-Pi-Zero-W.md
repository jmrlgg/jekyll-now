---
published: true
---
## Raspberry Pi Zero OTG Initial Setup

First off you will need to flash Raspbian lite or Full on your SD card. Once you have finished the flash, leave your SD card in your PC. We will need to change your config.txt and cmdline.txt files

##Down and dirty

**1.** Find your SD Card partition and open your ```config.txt``` and add ```dtoverlay=dwc2``` at the bottom

**2.** Now we will need to create a blank file named ```ssh``` with no extension. [ make sure ```.txt``` is deleted ]

**3.** Our next step is crucial that we keep the same syntax. This file requires a certain format for parsing or you will possibly run into errors. So we need to open ```cmdline.txt``` Now find ```rootwait``` and add a single space and add ```modules-load=dwc2,g_ether``` 

**Finally**

* Now we will eject out SD card, insert it into the Pi Zero.  

* Plug in your USB Micro Data cable into the Pi The first boot takes up to 2-3 Minutes. [ No need for external Power, your pc will power the Pi ]

* Once it has finished you will see a USB Ethernet device. This is your Pi Zero.

*  You can now SSH into it user ```ssh pi@raspberrypi.local``` as your address

* Your default pasword is raspberry 

You have now accessed your Raspberry Pi Zero through OTG ssh.


<meta name="twitter:card" content="One mans Blog" />
<meta name="twitter:site" content="@jmrlgg" />
<meta name="twitter:creator" content="@jmrlgg" />
<meta property="og:url" content="http://blog.yolodigi.com" />
<meta property="og:title" content="One mans Attempt at Blogging" />
<meta property="og:description" content="Tech, Media, Tutorials and daily life experinces." />
<meta property="og:image" content="http://graphics8.nytimes.com/images/2011/12/08/technology/bits-newtwitter/bits-newtwitter-tmagArticle.jpg" />
