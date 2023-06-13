---
title: "NVIDIA binary driver installation"
---

This is a guide to install the NVIDIA binary driver.

1. Download the driver from NVIDIA's site: https://www.nvidia.com/en-us/drivers/unix/.
2. Rebuild kernel inifsram: `sudo dracut --force /boot/initramfs-$(uname -r).img $(uname -r)`
3. Reboot.
4. Set non graphical target: systemctl set-default multi-user.target
5. Install the driver with: `sudo bash PATH_TO_THE_NVIDIA_DRIVER`:
  - It could say that it needs to disable nouveau with some configuration file, just let it do it (take note of where the file were written, just in case), reboot and launch the installation again.
6. Accept everything (you can read what it is during installation).
7. Set graphical target: systemctl set-default graphical.target
8. Reboot.
