# River's Kinesis Advantage Blackpill based controller board

This is a replacement controller board for the Kinesis Advantage keyboard.
It is a development of the kinBP by https://github.com/DmNosachev.

Changes from that one:
- Added piezo sounder, allowing for key clicks / beepy tunes.
- Added connector for the original Kinesis cable. There is no need to buy extra USB cables and hack up the case!
- Removed some unneeded connectors, that were for a custom thumb board I'm not using.
- Aligned thumb connector holes properly so you can use the original cable.
- Completely rerouted.
- N.B.: The pins used for the matrix are different - you must use the correct QMK configuration, also provided on my github.


## Build Notes

- There are two options for orientation of the function key connectors. Test it works before soldering in.
- Obtain qmk keyboard files from https://github.com/anm/qmk_firmware/ river branch.
- Build QMK with `qmk flash -kb kinesis/river -km river`.
- Flash with dfu-util
- Flash: Enter bootloader by holding BOOT0 button while resetting / powering on the board, then
  `dfu-util -a 0 -d 0483:df11 -s 0x8000000:leave -D kinesis_river_blackpill411_river.bin`.
  After flashing, you can also enter the bootloader by holding both shift keys and B on the keyboard.

More info at the parent project: https://github.com/DmNosachev/kinbp
