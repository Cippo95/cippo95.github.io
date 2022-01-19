---
title: "Valve's games have issues on Linux"
---

> I will format this post to look prettier in the future

In my free time I'm testing **Fedora 35** gaming capabilities.  
Valve seems to care about GNU/Linux succeeding as a gaming platform: 
  - They made and work on Proton,
  - The incoming Steam Deck will be based on Arch Linux,
  - Their games run natively on Linux.  

I have tested this last point and I tried Dota 2, CS:GO, Team Fortress 2... they all had problems.  

Before I show you how I have fixed my problems, I advise you to activate for every game the **gamemode**.
Just add to the launch options of the game this:  
`gamemoderun %command%`  

Game mode for me is a godsend, it fixes a lot of stuttering and I thank Feral Interactive for developing it.  

> In case check if it is already installed with:  
> `sudo dnf install gamemode`.  
> If you have other commands with %command% put only one %command% after all of them.
> For example I use mangohud (google it in case), so in my games I usually have "gamemoderun mangohud %command%".

**NOTE: All of what is said here is valid for Fedora 35 and could also depend on my personal PC build!**  

# Dota 2

**ISSUE:** The game by default just hangs/locks now and then, it is very annoying, you will surely notice it. 

**WHAT WORKED FOR ME:**  
Disable Steam shader precaching:
Steam settings -> Shader Pre-caching -> Disable it.  

The game also with Nvidia 495 drivers and Vulkan API just fails to close in game, close it from Steam.  
With 470 it hasn't this problem, so this is something Nvidia has to fix I think.

# CS:GO

**ISSUE:** It just crashes on launch... Valve... really.

**WHAT WORKED FOR ME:**  
`sudo dnf in gperftools`  
`cd ~/.local/share/Steam/steamapps/common/Counter-Strike Global Offensive/bin/linux64`  
`mv libtcmalloc_minimal.so.0 libtcmalloc_minimal.so.0.bak &&`  
`mv libtcmalloc_minimal.so.4 libtcmalloc_minimal.so.4.bak`  
`ln -s /usr/lib64/libtcmalloc_minimal.so.4 libtcmalloc_minimal.so.0`  
`n -s /usr/lib64/libtcmalloc_minimal.so.4 libtcmalloc_minimal.so.4`  

Then put `-novid` in the launch option because apparently also the initial video hardlocks the game... wow.  

# Team Fortress 2

**ISSUE:** This game will launch and play fine... a part a lot of missing audio!  
If you open TF2 console you will see something complaining about selinux and mp3 impossibile to decode.

**WHAT WORKED FOR ME:**  
`ausearch -c 'hl2_linux' --raw | audit2allow -M my-hl2linux`  
`semodule -X 300 -i my-hl2linux.pp`  

Another interesting thing is that TF2 has mouse sensitivity doubled, I have read that is because they use some old library with this bug.
Set half of your usual sens in Source games and you are good to go.

So yeah Valve is doing great stuff for the Linux community... but also should check if their own games work properly.

Have fun!
