# t430-coreboot
coreboot rom for thinkpad t430

12m image for the x230, with vga in "native" mode, seabios and all the secondary payloads added.

seabios time-wait-menu reduced to 1 second only.

Bootspash added.

me.bin file has been me_cleaned

to flash it internally, if already running coreboot and bios unlocked:
sudo flashrom -p internal:laptop=force_I_want_a_brick -w m4rc0t430.rom --ifd --image bios -V

To flash exeternally the roma needs to be splitted in 2

To compile a different version the "config" file could be a starting point.
