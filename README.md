# t430-coreboot

coreboot V 4.13 rom for thinkpad t430 featuring seabios v. 1.14.0 https://seabios.org/Releases#SeaBIOS_1.14.0
commit 5c186c6777c9438ff4681929c9c25c98dee28bef
Secondary payloads added https://www.coreboot.org/Payloads
Nvramcui
Coreinfo: https://www.coreboot.org/Coreinfo
Nemtest: https://www.coreboot.org/Memtest86
Tint: https://www.coreboot.org/Tint


- m4rc0freet430.rom uses libgfxinit at the resolution 1024x768 and has no support to intel wifi cards and bluetooth

- m4rc0t430.rom instead uses the vga rom and supports intel wifi cards and bluetooth

In both cases the 12m images have seabios and all the secondary payloads added and:

1) seabios time-wait-menu reduced to 1 second only.

2) Bootspash added.

3) me.bin file has been me_cleaned

how to flash:

- internally, if already running coreboot and bios unlocked:

sudo flashrom -p internal:laptop=force_I_want_a_brick -w name.rom --ifd --image bios -V

or

sudo flashrom -p internal:laptop=force_I_want_a_brick -w name.rom -V


- externally the rom needs to be splitted in 2

dd if=name.rom of=coreboot8.rom bs=1M count=8

dd if=name.rom of=coreboot4.rom bs=1M skip=8

then you can flash the coreboot roms with final number 8 and 4 on the 8m nd 4m chips.


To compile a different version the "config" file could be a starting point.

To see how this (or my others built images) works, just have a look into my youtube https://www.youtube.com/user/marcolinoxz
