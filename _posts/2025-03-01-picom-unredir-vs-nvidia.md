---
title: Picom's unredir option issue with NVIDIA's 570 branch drivers
---

Yesterday I have discovered that Picom's `--unredir-if-possible` option doesn't work well with the new NVIDIA's 570 branch drivers.
This option is necessary to use G-Sync while playing games.

I have Picom 12.4 (the latest version right now) and the issue manifests when using the glx backend, the one giving me the best vsync results.

The issue is that while enabling the second monitor everything goes black, with only the mouse remaining visible.
Entering the second virtual console (Alt+Ctrl+F2) and killing Picom restores the correct output.

Going back to the 550 branch fixes this issue.

PS: With the new 570 drivers I have also noted that Control (which I use to check if the driver works fine) doesn't start.
