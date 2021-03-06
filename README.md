# Debian 10 Porting on KM-BBB Expansion Board.

#### Clone this [debina10-km-bbb] reposiotry in your home folder under KM_GITHUB.
```sh
$ mkdir ~/KM_GITHUB
$ cd ~/KM_GITHUB
$ git clone https://github.com/kernelmasters/debian10-km-bbb.git
$ cd ~/KM_GITHUB/debian10-km-bbb
```

## Install Debian 10 Prebuilt images
### Using SDCard:
1. Enter prebuilt Folder

   `$ cd ~/KM_GITHUB/debian10-km-bbb/prebuilt`
2. Format SD Card with 1 partition and load boot loader images [MLO, u-boot.img] and debian 10 rootfs using the below script.

   `$ sudo ./km-bbb-sdcard-prebuilt-debian10.sh --mmc /dev/[drive]`
   
   "drive" is sdb or mmcblk0. find out using dmesg command after inserting sd card.
   script run 5 to 10 minutes.   
3. Insert SDcard on BBB target and press switch2 and power on board. "km_bootmenu" choose sd card option and now BBB booting from SD card.
4. By default `username:km; password:km` enter login prompt. And update software packages otherwise sudo permission problem encounter.

   `$ sudo apt-get update`


## MLO, U-boot & Kernel Versions

MLO [SPL] Version: 
`U-Boot SPL 2019.04KernelMasters-g9d37c406 (Jan 10 2021 - 23:27:22 +0530)`

U-Boot Version:
`U-Boot 2019.04KernelMasters-g9d37c406 (Jan 10 2021 - 23:27:22 +0530)`
`Source: KM_GITHUB/beagleboneblack-uboot.git - Tag: km-bbb`

Kernel Version:
`Linux KM-BBB 4.19.94-gc8fc2bfff-dirty #1 SMP Fri Dec 25 17:17:24 IST 2020 armv7l GNU/Linux`
`Source: KM_GITLAB/beagleboneblack-kernel.git - Commit ID:25ae2381`
