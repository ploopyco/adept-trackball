# Appendix D: QMK Firmware Programming


# Working with QMK

Ploopy devices are fairly easy to program and reprogram, thanks to the excellent work by all of the developers and maintainers of the [QMK firmware suite](https://github.com/qmk/qmk_firmware).

## Madromys? What's that?

`madromys` is our internal codename for the Ploopy Adept. We don't always know what we're going to call the devices as we're designing them, so we assign codenames to them. This naming convention is also present in some public places, such as the QMK repository. If you see `madromys` while you're working with QMK, just know that the Adept and `madromys` are the same thing.

## Before you begin

If you have never used QMK before, go through [all of the steps in the QMK guide to set up your environment](https://docs.qmk.fm/#/newbs_getting_started).

QMK was built for keyboards, so you'll see lots of references to code that looks like the following:

`-kb <keyboard>`

Whenever you see that, use the following syntax:

`-kb ploopyco/madromys/rev1_001`

and you'll be fine.

## Building the Ploopy device firmware

With your terminal window open and pointed at your QMK build environment, compile the firmware with the following command:

`qmk compile -kb ploopyco/madromys/rev1_001 -km via`

Alternatively, you can invoke the Makefile directly with the following:

`make ploopyco/madromys/rev1_001:via`

If you wish, you can use the default keymap (with `qmk compile -kb ploopyco/madromys/rev1_001 -km default` or `make ploopyco/madromys/rev1_001:default`). However, the VIA keymap is particularly interesting because it allows for customization of the trackball's functions without reflashing the firmware, through the use of the convenient [VIA software package](https://github.com/the-via/releases/releases). It's incredibly handy, so definitely check it out.

For more details on building QMK firmware in general, see the [QMK firmware guide](https://docs.qmk.fm/#/newbs_building_firmware).

## Putting the Ploopy device into bootloader mode

Putting the Ploopy device into bootloader mode is very easy.

1. Unplug it from your computer.
2. Hold down the Bottom Left button on the Adept.
3. Plug the Ploopy device into your computer.
4. The computer should recognise that a mass storage device was just plugged in. Once this is done, you should be able to drag and drop files onto the Ploopy device, as if the board was a USB drive. Feel free to remove the tweezers or paperclip at this point.

And that's it. While plugged in this way, the Ploopy device will accept new firmware.

If you want to upload a new firmware file (a ".uf2" file, like "ploopy_adept_v42069" or something), just drag it into the folder, and it'll automatically install on the Ploopy device and restart itself.

Whenever you want to put new firmware onto the Ploopy device, go through these steps again.

**TIP**: If your firmware is in some kind of strange state and uploading new firmware isn't fixing it, try uploading [a flash nuke](https://learn.adafruit.com/getting-started-with-raspberry-pi-pico-circuitpython/circuitpython#flash-resetting-uf2-3083182) to the Adept before flashing the new firmware. It wipes the memory of the Adept completely clean, which can help clear a few types of errors.

## Putting the Ploopy device into bootloader mode if it's bricked

Putting the Ploopy device into bootloader mode if it's bricked is a bit more involved, but still doable.

1. Unplug it from your computer.
2. Open it by removing the screws in the base and removing the top.
3. Look for a pair of vias (gold-plated holes) on the board. You can see where they're located [in this photo](https://ploopy.co/wp-content/uploads/2023/11/boot.jpg).
4. Get a paper clip (non-insulated, i.e. no plastic shit covering it) or a pair of tweezers, or some wire. Whatever you've got on hand that's metal.
5. Stick the paper clip or tweezers into the holes. You're trying to form an electrical connection between the two holes.
6. While you've got the two vias connected with your metal bridge, plug the Ploopy device into your computer.
7. The computer should recognise that a mass storage device was just plugged in. Once this is done, you should be able to drag and drop files onto the Ploopy device, as if the board was a USB drive. Feel free to remove the tweezers or paperclip at this point.

And that's it. While plugged in this way, the Ploopy device will accept new firmware.

## And that's it!

Happy customizing!
