---
title: "NVIDIA binary driver installation on Fedora"
---

This is a guide to install the NVIDIA binary driver of Fedoras systems.  
> I will keep this extremely concise.  

1. Download the driver from NVIDIA's site: https://www.nvidia.com/en-us/drivers/unix/
2. Rebuild kernel initramfs:  
`sudo dracut --force /boot/initramfs-$(uname -r).img $(uname -r)`  
3. Set non graphical target:  
`systemctl set-default multi-user.target`  
4. Reboot.
5. Install the driver with:  
`sudo bash PATH_TO_THE_NVIDIA_DRIVER`  
> Here, the installation could complain about Nouveau and that it needs to disable it with some configuration file, just let it do it (take note of where the file are written, maybe you need to delete them in the future), reboot and launch the installation again.  
> 
6. Accept everything (you usually want everything of what is proposed in this case).
7. Once the installation is finished, set graphical target:  
`systemctl set-default graphical.target`  
8. Reboot.
