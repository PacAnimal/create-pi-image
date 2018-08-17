# create-pi-image
A script for creating compressed minimal size images from a Raspberry Pi sd card

This script will:
* Run e2fsck on the root file system
* Erase logfiles, such as bash_history and stuff in /var/log
* Erase the test.h264 video file
* Wipe resolv.conf
* Defragment the root file system
* Resize the root file system to the minimum size, according to resize2fs
* Resize the root partition to match the file system
* Zero-fill remaining free space on both partitions
* Create an image file of the exact length of the partitions
* Compress the image file to .zip, using the “ultra” setting for compression 

Required runtime tools include:
* dd
* 7z
* resize2fs
* dumpe2fs
* e4defrag 

This script is intended for Raspbian SD card images only, and may not work as intended with other distributions.
