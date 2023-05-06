---
title: "My configuration for smooth audio on Fedora 37"  
---

> I'll develop the full article time by time.

My PC with Fedora 37 has a lot of crackling with audio.

My issues:
- USB microphone crackling in recordings, very noticeable in OBS, noticeable with Audacity.
- Audio output crackling, some application cause this problem a lot such as games, Discord, mpv etc.

My setup:
- CPU: AMD Ryzen 3500X
- Motherboard: MSI B450 Gaming PLUS Max
- RAM: 2x8 GB 3000 MHZ (Crucial Ballistix Sport LT)
- Graphics Card: NVIDIA RTX 2060 Super (driver 525.116.03 from NVIDIA)
- Sound card (PCI-E): ASUS Xonar DGX
- USB microphone: Fifine T669

The soundcard is not the problem since the output crackling happens also with the onboard audio and graphics card audio (with Display Port).  
The audio output can be helped setting in `pipewire.conf` `default.clock.min-quantum = 1024`.  
I recommend to do this with an user configuration copying the file in `/usr/share/pipewire/pipewire.conf` in `~/.config/pipewire/pipewire.conf

The way that I have fully fixed my issue is by installing a real time kernel (yes, it isn't something a casual user should do!).

- Info to the real time kernel here:  
https://discussion.fedoraproject.org/t/audinux-repository-updated-for-fedora-37/44113    
- You need to install the nvidia driver package with an environment variable to enable the installation on rt kernels, infos here:  
https://gist.github.com/pantor/9786c41c03a97bca7a52aa0a72fa9387  
- Use Jack APIs (with pipewire-jack) in OBS to record your mic and audio for the best experience: install qjackctl and learn how to connect your audio input, outputs.    
- Enjoy! Now everything works really well, maybe some occasional and rare xrun but that's it.

Good luck!

PS: This blog post should be sufficiente, but I have opened a pipewire issue where you can read some more stuff:  
https://gitlab.freedesktop.org/pipewire/pipewire/-/issues/3190  
