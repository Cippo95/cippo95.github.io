---
title: "Pairing adb (android tools) on Fedora 37"  
---

I use OBS Studio with Droidcam OBS to use my smartphones as a webcam.    

I use the flatpak version of OBS Studio, which is considered the "official distribution" nowadays.    
This flavour of OBS works easily with Droidcam OBS using a local WiFi, but also with adb if you install it:  
`sudo dnf install adb`

> Fedora converts in `sudo dnf install android-tools`, you can install it also this way.  

The phone I'm using for this purpose right now is a Xiaomi Mi A2 Lite.  
To use adb you need to enable the usb debug option in the developer settings.  

> To enable the developer settings you need to tap multiple times the "build number" in the settings.  

After this my phone wouldn't pair with my computer: a window to accept the pairing should appear on the phone.  
Running `adb devices` should tell you what devices are connected and accessible: my phone wasn't authorized.  

Looking online it was a mess until I have looked at the arch wiki (god bless this wiki).  
On the wiki a "tip section" says that some device needs to be connected with the MTP or PTP option, 
in my case there was only the PTP option and it solved my pairing problem (the window to accept the pairing appeared on the phone).  
