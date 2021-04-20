# termux-prefix-switcher
This Utility Allows you to switch to Termux 32-bit on 64-bit devices!

This tool is useful if:
* Testing and Compiling 32-bit Packages
* Emulate 32-bit Distros!
* A Problem Reproducer

With this utility, you probably want to run box86 on your device 😬

# System Requirements
* Running atleast Android 7 and Above
  * ARM64 if you have arm 64-bit processor
  * x86_64 if you have intel 64-bit processor
  * Your OS should be 64-bit, and not 32-bit
* Atleast 4gb of storage (It backs up your Termux 64-bit prefix for reverting)

# Switching
If you have those requirements fulfilled, you can download the `termux-prefix-switcher` script in this repository

Then run `termux-prefix-switcher switch` to switch to 32-bit environment

*Ensure you have all your files saved before switching, to avoid data loss*

During the switching process, it backs up your current Termux prefix so you can revert stuff later

Also note that it doesn't install packages automatically so you will need to reinstall them again if possible

After the switching process, you can find it out by typing `uname -m` on your device, and you should be in 32-bit if `uname` reports `armv8l` or `i*86`

# Reverting
If you're done playing around with 32-bit, there's always a chance to go back if something goes wrong

To Revert back from your previous installation, you can type: \
`termux-prefix-switcher revert`

this will erase 32-bit environment and switch you back to previous 64-bit Installation (if you haven't deleted it)

If you want to backup your 32-bit Installation, see [Backing up Termux](https://wiki.termux.com/wiki/Backing_up_Termux) page

# Permanently Switching to 32-bit
If you feel happy with 32-bit and you want to save space on your device, you can safely delete the previous 64-bit prefix by doing: \
`rm -rf $PREFIX/../usr64-backup`

# Known Issues
* Running native 64-bit programs may throw errors about `termux-exec` if that happens, you may do `unset LD_PRELOAD` \
*However if running it under proot, well you probably need to run 32-bit instead of 64-bit*

* Running Chromium in 32-bit Linux Distro, you will get segmentation failures, although a successful workaround has been stated [here](https://github.com/termux/proot/issues/107)

# Installation

Copy
```
wget https://github.com/suhan-paradkar/termux-prefix-switcher/releases/download/v1.0/termux-prefix-switcher_1.0_all.deb
dpkg -i termux-prefix-switcher_1.0_all.deb
```
