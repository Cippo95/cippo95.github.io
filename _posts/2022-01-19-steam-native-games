--
title: "Valve Linux native games often have issues" 
--

> I will format this post to look prettier in the future

In my free time I'm testing a little *Fedora 35* gaming capabilities.
I was trying to play Dota 2, CS:GO, Team Fortress 2 and they all had problems.
These games have a native port for Linux but they all had stuff to fix.

After you have fixed them I advise to use the gamemode by adding "gamemoderun %command%" in the game launch options.
Game mode fixes a lot of stuttering, it is really a god send for me, thank you Feral Interactive for developing it.
PS: In case check if it is already installed with `sudo dnf install gamemode`.

*All of what is said here is valid for Fedora 35.*

# Dota 2

The game by default just hangs now and then, it is very annoying.

FIX:
Steam settings -> Shader Pre-caching -> Disable it.

The game also with Nvidia 495 drivers just fails to close in game, close it from Steam.

# CS:GO

It just crashes on launch... Valve please CS:GO is broken, fix it.

FIX:
`sudo dnf in gperftools`
`cd ~/.local/share/Steam/steamapps/common/Counter-Strike Global Offensive/bin/linux64`
`mv libtcmalloc_minimal.so.0 libtcmalloc_minimal.so.0.bak &&`
`mv libtcmalloc_minimal.so.4 libtcmalloc_minimal.so.4.bak`
`ln -s /usr/lib64/libtcmalloc_minimal.so.4 libtcmalloc_minimal.so.0`
`n -s /usr/lib64/libtcmalloc_minimal.so.4 libtcmalloc_minimal.so.4`

Then put `-novid` in the launch option.

# Team Fortress 2

This game will launch and play fine... a part a lot of missing audio!

FIX: 
`ausearch -c 'hl2_linux' --raw | audit2allow -M my-hl2linux
semodule -X 300 -i my-hl2linux.pp`
