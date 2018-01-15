---
published: true
---
---
layout: post
title: Windows 10 Tweaks and Tips
---
# Windows 10 Tweaks and Tips

## Speed, anti-spying, anti-track, and unwanted packages.

If you want a cleaner, smaller image, better browsing, better gaming... The list goes on and on with endless posibilities using these simple tweaks for your windows 10 install. 

If you have a Creators Update Version. 1753, This is a HUGE Benefit. If you have the LTSB 1607. This is the final touch to disengage telemetry, tracking, and to block unwanted ip's 
___________________
<!--more-->
Download and install the following..
[install_win_tweak.exe](https://drive.google.com/open?id=1TTfdXjspg8XG_KhFj8zUi4abxFHDkWK2)
[install_wim_tweak_NET.exe](https://drive.google.com/open?id=159FTN10q5WjPJUN5BYllLrsXeavRHWmE)
[Source](https://drive.google.com/open?id=1ysjFE2LZ35oervOK0jSU3SP__jElYhnm)


[![IMAGE ALT TEXT HERE](https://1.bp.blogspot.com/-HYffEcaWjEM/Wg2zODyPphI/AAAAAAAAEic/EF6XeIGZiG8D24AGztRwfTiuPQUqiXMlQCLcBGAs/s200/wim.png)](https://1.bp.blogspot.com/-HYffEcaWjEM/Wg2zODyPphI/AAAAAAAAEic/EF6XeIGZiG8D24AGztRwfTiuPQUqiXMlQCLcBGAs/s1600/wim.png)

________________________________
Below is special command paramaters that you can use for un-hiding packages and removeing, from a .iso even. 

```
*/h will restore them to default (must use without /h first)
*/n will not create backups (faster)
*/d will not delete owners keys.
*/m is no longer needed, will do the task by default
*/l will output a list of all packages to a text file.
*/o will use currently installed image.
*fixed a bug where it did not work if there was a space in the mountpath.
*/c <PackageName> will un-hide specific package
* using /r with /c will remove the package
```

install_wim_tweak.exe /?
This will show all available options..

install_wim_tweak.exe /p < MountPath >
This will unhide all the packages in the selected image

install_wim_tweak.exe /o
This will unhide all the packages on the currently installed OS

install_wim_tweak.exe /p < MountPath > /l
This will list all the packages available in the selected image and write them to a text file in the same directory.

install_wim_tweak.exe /o /l
This will list all the packages available on the installed OS and write them to a text file in the same directory.

install_wim_tweaks.exe /p < MountPath > /c Microsoft-Windows-.........
This will just inhide the selected component from the selected image, can also be used with /o. If you add /r at the end it will remove the package.

___________________
### Below Is a few packages I recommend uninstalling

        
        Microsoft-OneCore-TroubleShooting-WOW64-Package 
        Microsoft-OneCore-TroubleShooting-Package~31bf3856ad364e35 
        Microsoft-OneCore-AllowTelemetry 
        Microsoft-Windows-OneDrive-Setup-Package~31bf3856ad364e35~amd64~~10.0.10240.16384 
        Windows-Defender-Group-Policy-Package~31bf3856ad364e35 
        Windows-Defender-Client-WOW64-Package~31bf3856ad364e35 
        Windows-Defender-Client-Package~31bf3856ad364e35 
        Windows-Defender-AM-Default 
        Microsoft-Windows-Security-SPP-Component-SKU 
