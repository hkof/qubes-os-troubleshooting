# qubes-os-troubleshooting
some tips to fix common issues when installing/running qubes os
## Installation:
### nvidia gpu
If your laptop has an nvidia gpu most likely you will the installation loading screen will freeze or end up with this error message 'X startup failed, aborting installation'.<br/>

One way to fix it is to disable your nvidia driver(nouveau) and use your internal gpu (usually supported by the kernel):
1) boot into grub menu, edit the first option by pressing the tab key to enter edit mode.
2) right after `quiet rhgb`, add the following:<br/>`nouveau.modeset=0 rd.driver.blacklist=nouveau video=vesa:off`
3) Now you should be able to start qubes installer.

### non supported wireless card
If you get stuck at the last stage of installtion, while configuring the net-vm. Most likely your wireless card is not supported, you need to replace it with another one that is supported by the kernel.


## After Installation:
### sleeping mode
My laptop won't wake up from sleep mode:<br/>
update your kernel to the latest version, using:<br/> `sudo qubes-dom0-update kernel-latest`
