# qubes-os-troubleshooting
some tips to fix common issues when installing/running qubes os
## Installation:
If your laptop has an nvidia gpu most likely you will the installation loading screen will freeze or get this error message "X startup failed, aborting installation".<br/>

One way to fix it is to use your internal gpu (usually supported by the kernel):
1) boot into grub menu, edit the first option by pressing the tab key to enter edit mode.
2) right after quiet rhgb, add the following: nouveau.modeset=0 rd.driver.blacklist=nouveau video=vesa:off
3) Now you should be able to start qubes installer.

If you get stuck at the last stage of installtion, while configuring the net-vm. Most likely your wireless card is not supported, you need to replace it with another one that is supported by the kernel.
