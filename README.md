# Flash-CHIP
Ready to use Flash environment for the C.H.I.P Single Board Computer

Simplyfies the Flashing Process for the C.H.I.P and PocketC.H.I.P Computer. 

Note the URL for the image files only contains the last stable NTC images; you'll need to download additional archived images from the archive.org link below.

## Instructions
1. Remove the C.H.I.P from its case (in case you have a Pocket C.H.I.P).
2. Connect the FEL and a GROUND pin of the C.H.I.P (for example, with a paperclip).
3. Connect the C.H.I.P micro USB port to a USB port of your Linux machine.
4. In the Linux machine:
    - run ` git clone https://github.com/thore-krug/Flash-CHIP.git` to clone this repository.
    - `cd` into the location where you stored this repository.
    - run `chmod +x Flash.sh`
    - run `./Flash.sh`
    - Select the version you want to install.
    - Wait until the installation finishes.
    - Enjoy!

## Troubleshooting 
### General Issues
1. Kill the Script with ctrl + C 
2. Read the output if something is not installed or Permissions are missing 
3. Just restart the Script (fixes most of the Problem with FEL and Fastboot ) 
4. If this does not help reboot, retry
5. Open an Issue on this Git Repo. 

### The script times out waiting for fel
This error is related to an insufficient amount of power provided by your USB port to the C.H.I.P.  
If you have an external `5V` power supply, you can connect it to the `CHG-IN` pin of your C.H.I.P. to provide sufficient power.    
Alternatively try a different (shorter, or higher quality) USB cable and check if your host PC has USB power saving enabled.  

Try a known good environment and/or fallback to sunxi-tools 1.4.1 (note building
from source may require a small Makefile patch, depending on build env).

Recently tested on raspberrypi 3 running latest 2021-12-02-raspios-buster-armhf-lite
and using sunxi-tools 1.4.1-1 debian pkg.

```bash
git clone https://github.com/thore-krug/Flash-CHIP.git
wget http://ftp.debian.org/debian/pool/main/s/sunxi-tools/sunxi-tools_1.4.1-1_armhf.deb
sudo dpkg -i sunxi-tools_1.4.1-1_armhf.deb
sudo apt-mark hold sunxi-tools
cd Flash-CHIP
chmod +x Flash.sh
```

Open `Flash.sh` in your favorite editor and delete the line `sunxi-tools \` then save an exit.

```bash
sudo ./Flash.sh
```
Type s and Enter (or your choice of rootfs) then wait.  Make a coffee...  Enjoy!


## more info

* Chip data on archive.org: https://archive.org/details/C.h.i.p.FlashCollection
* backup website with stable images: http://chip.jfpossibilities.com/

Older links:

* https://www.reddit.com/r/ChipCommunity/comments/lhs0p6/how_to_flash_chip_on_rpi4_2021_guide/
* https://medium.com/@0x1231/nextthingco-pocket-c-h-i-p-flashing-guide-3445492639e
