---
title: "My configuration for smooth audio on Fedora 37"  
---

I'll develop the full article time by time.

My issues were: USB microphone crackling in OBS recordings, audio output crackling if the application needed low quantization (use pw-top to see the requested quantization), I have tried many settings but the first problem wasn't fixable, the second one got better when setting a minimum quantization of 1024... beware that some application will get skipping audio if you do this but in general works better than hundreds of xruns/cracks every minute when the problem gets serious (Discord voice-chat, using mpv, playing games).

My setup is:
CPU: AMD Ryzen 3500X
Motherboard: MSI B450 Gaming PLUS Max
RAM: 2x8 GB 3000 MHZ
Graphics Card: NVIDIA RTX 2060 Super (driver 525.116.03 from NVIDIA)
Sound card (PCI-E): ASUS Xonar DGX
USB microphone: Fifine T669

My steps that I will develop:

-Install a real time kernel, infos here:
https://discussion.fedoraproject.org/t/audinux-repository-updated-for-fedora-37/44113  
-Install the nvidia driver with an environment variable to enable the installation on rt kernels, infos here:  
https://gist.github.com/pantor/9786c41c03a97bca7a52aa0a72fa9387  
-Use Jack (with pipewire-jack) in OBS to record your mic: install qjackctl and learn how to connect your audio input, outputs.  
-Enjoy! Now everything works really well, maybe some occasional and rare xrun but that's it.

For all this steps just focus a little, it is not that difficult to do when you know were to look, good luck!
