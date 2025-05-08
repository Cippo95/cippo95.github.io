---
title: My setup at boot
---

*Work in progress...*

1. GRUB settings:
```
GRUB_TIMEOUT=5
GRUB_DISTRIBUTOR="$(sed 's, release .*$,,g' /etc/system-release)"
GRUB_DEFAULT=saved
GRUB_SAVEDEFAULT=true
GRUB_DISABLE_SUBMENU=true
GRUB_CMDLINE_LINUX="quiet splash preempt=full video=DP-2:d rd.driver.blacklist=nouveau modprobe.blacklist=nouveau"
GRUB_DISABLE_RECOVERY="true"
GRUB_ENABLE_BLSCFG=true
```
>Much of this is default, I find `video=DP-2:d` interesting, it disables my second monitor during boot.

2. Plymouth
3. No display manager
   After trying a lot of them I don't use a display manager, I just type my username and password on tty1 (the terminal that appears after boot) and automated on that terminal the launch of the X server.
4. Start the X server at boot
   To start the X server when I have successfully typed my username and password I added this to my `.bash_profile`:
```
# Start X server
if [[ -z $DISPLAY ]] && [[ $(tty) == /dev/tty1 ]]; then
    exec startx
fi
```
