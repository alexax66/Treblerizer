# Android Partition Treblerizer

This tool able to seamlessly create / remove the vendor partition from within TWRP

## INTRODUCTION

This tool able to create and remove the vendor partition from TWRP, without required computer.
The TWRP flashable ZIP can create and remove the Vendor partition from the system or userdata
partitions without a computer and without wiping the files in the mother partition in the
recommended configuration.

This tool will try to resize the mother partition without wiping it, both when creating and
removing the vendor partition. Nonetheless it can be done only when the mother partition is ext4,
only when the vendor partition is at the end of the mother partition, and when the mother partition
is not encrypted. The recommended configuration is what you get when selecting the first choice
in every option: splitting 512 MB from the end of the system partition. A reboot is required after
patching the partition table since the kernel has to reload it before doing any other thing.

## REQUIREMENTS

Due to the use of a key detection binary, it is compatible only with ARM and ARM64 devices
running TWRP. I have tested it in the Samsung Galaxy A3 2016 but It should work in some
compatible device. I made it this way so other legacy devices could transition to Treble
ROMs + GSI, and Android Pie. Please let me know about other devices using this tool successfuly.

## INSTALLATION

WARNING, THIS SOFTWARE COULD WIPE ALL THE DATA IN YOUR DEVICE, INCLUDING THE INTERNAL STORAGE.
IT REQUIRES TWRP CUSTOM RECOVERY IN AN UNLOCKED DEVICE, OTHERWISE YOUR DEVICE COULD BE BRICKED.
!!! Whatever you do, it is at your own risk !!!

### Either for creating or removing a vendor partition, follow these steps:

    - Download the TWRP ZIP tool to your External SD card.
    - Boot to TWRP recovery, under Install, flash the ZIP file as any other ROM or MOD file to execute the tool.
    - Reboot to recovery again to ensure the changes are applied properly.
    - In some cases you will need to format the mother partition after adding or removing the vendor partition next to it.

## CREATE A VENDOR PARTITION

### So far these are the available options:

    - Mother partition selection: system / userdata
    - Split position: Splitting from the end / start of the mother partition.
    - Vendor partition size: 512 / 256 MB

## REMOVE THE VENDOR PARTITION

Should a Vendor module partition exists, Treblerizer offers to remove it, returning to a Non-Treble
partition table. It will return the space to the mother partition, system or userdata. So,
older non Treble ROMs could be flashed after the mandatory reboot.

## DOWNLOAD
[Repartitioning_v0.6_a3xelte.zip](https://github.com/alexax66/Treblerizer/raw/master/Download/Repartitioning_v0.6_a3xelte.zip)

## LICENSE
C'mon, it's just a script. Use this source in your projects but don't forget to give credit!

## CREDITS
- @Oki for his [idea and script](https://forum.xda-developers.com/axon-7/development/tool-party-v0-1-vendor-partition-t3831517)
- @someone755 for the [keycheck](https://github.com/someone755/kerneller/blob/master/extract/tools/keycheck) binary
- @Zackptg5 for the V4A install script that inspired this project.
