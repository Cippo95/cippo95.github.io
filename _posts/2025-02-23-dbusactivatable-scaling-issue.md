---
title: DBusActivatable in .desktop files messes up with scaling
---

I use a 2160p screen with 200% scaling because I really like the sharpness it achieves.  

Sadly some app always refused to scale according to my scaling settings.  
Apps like this are Gnome Disks, EasyEffects, Flatseal etc. and they drove me nuts.  

I have found out that the culprit is a setting on their .desktop file:  
`DBusActivatable=true`  

Remove this setting if you don't need what it is providing (I don't) and enjoy.  
> Probably you can also put it to false with the same effect.

PS: I have found out that these apps behaved correctly when launched from the terminal, at that point my intuition made me look at the .desktop files, but it was an issue that I had for years and I have never found the solution... up until now.
