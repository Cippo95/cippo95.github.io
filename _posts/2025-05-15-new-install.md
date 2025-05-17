---
title: New Fedora Install
---
I decided to upgrade from 1 TB SSD to 2 TB and I have decided to reinstall Fedora to start from scratch (the previous install was around 3 years old).
I think that starting from scratch is interesting to see how much time I get to reconfigure the PC as I want.

In this article I will report a diary of the first 2-3 days (I have written down what I was doing).
Work in progress now I'm just writing what I have done with some translation on the fly from italian to english:

- After having done the install key and rebooted into it monitors order was not correct and the 2160p screen had tiny UI (it is normal with the default of 96dpi);
- xfce4-terminal is the default (and it is my preferred terminal), opening it there info about how to install the operating system;
- Everything is fine to set, the only thing that seems difficult is to set some SSD overprovisioning, for now I leave the default (I hope that GNOME Disks will let me resize the partition later);
- Leave the root user enabled, who know maybe I will need it;
- First boot was ok, but with Fedora 42 new background;
- I tried to use the extenal SSD with the NVME to USB converter, it works great;
- I want to install the NVIDIA drivers from Fusion;
- To do so the system does a full update, while doing so I have copied my i3wm config + scripts;
- I don't have rofi so I install it;
- After the full update I can finally install NVIDIA drivers, it is a little long and I have to wait the module for build;
- There's no .Xresources by default, I try to use vim but needs to installed (there's the standard vi);
- I put dpi 192 in the .Xresources and now the 2160p monitor is how I like it, the 1080p has huge UI but it will be handled by my configuration;
- i3bar is not configured as I want
- picom is not installed
- I install keepassxc for my passwords, using DNF (but maybe here was fine with flatpak);
- I install steam... but it doesn't work and I find a topic online when they say to launch it with a particular environment variable and it works;
- Flatpak needs to be installed and I install it;
- pavucontrol was already there, but I use the qt version, so I have disinstalled the gtk one and installed the other one... the UI is huge and it lacks icons (but I know how to fix the latter one);
- Trying to install OBS is not found so I search online the repo and it sets up also the flathub standar repo;
- I install mangohud;
- I remove lightdm but everything goes black so I don't think it is really removed, I will set bash profile to start X, I don't like desktop managers;
- I install the breeze icon to solve the issue with pavucontrol-qt (but I don't like these icons);
- I have to set my custom theme for rofi and I find it in /usr/share/rofi/themes on the old SSD;
- Alt+A to accept the theme for rofi doesn't work, so I have manually created the config.rasi;
- I have enabled Firefox compact mode (I don't like the standard one);
- I have downloaded gnome-colors-icon-theme, I really like these icons, in particular the blue ones!
- I have copied my i3 status config so now i3 bar looks as I want;
- Copied Mangohud config from the old SSD;
- I have removed lightdm for good (probably from TTY2)
- I ahve removed mousepad (but I will reinstall it or install vscode/codium);
- I have installed heroic with flatpak but mangohud doesn't work so I have installed it then with its rpm image;
- The mouse icon is little (also here I know how to fix it);
- Terminal fonts on start are little, I have to install terminus-font and configure the virtual console;
- mouse speed is ok (but it is handled by my configuration);
- I had to install xset to make my config work correctly to disable monitor switching off;
- NVENC is not detected by Flatpak OBS, I rembered something about this and fixed it with a command in my configuration;
- Installed lxpolkit to have a graphical request of credentials (but maybe I need also some other package);
- I installed thunar-archiver-plugin and xarchiver to extract zip files;
- I installed the printer drivers copied the zip from the old SSD and unzipped them;
- Pipewire by default can go down to 32 quantum, playing games I had it at 128 and audio was all over the place, I have limited it at 256;
