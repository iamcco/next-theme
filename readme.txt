## rEFInd Next theme

[rEFInd](http://www.rodsbooks.com/refind/) is a simplistic boot manager for UEFI
based systems. This is a clean and minimal theme for it.

![rEFInd Next](http://sdbinwiiexe.deviantart.com/)

### Usage

To use this theme you'll want to clone it into the same directory as your rEFInd
efi executable (usually `/boot/EFI/refind/`). Then you will want to add the following line to the end of your `refind.conf`:
	include next-theme/theme.conf


To set the appropriate background image, edit the “theme.conf” file in TextEdit and change the banner line to direct to whichever image file corresponds to your mac’s native resolution.
E.g. If your native resolution is 1440x900, you’d change the line to the following:
	banner next-theme/background_900.png

To make an icon appear when loading using graphical boot, open boot_bg.png file in your image editor of choice, and just copy the operating system’s os_ icon over top of the background.  Then save the new image using the boot_ prefix.  A few examples have been included (windows, linux, ubuntu, linux mint, unknown)

To set the icons for your entries you will want to add the `icon` configuration
to each menuentry which points to the icon under `next-theme/icons` that you
would like to use for that entry.

Here's an example configuration:

````
menuentry "Arch Linux" {
	icon /EFI/refind/next-theme/icons/os_arch.png
	loader vmlinuz-linux
	initrd initramfs-linux.img
	options "ro root=UUID=dfb2919d-ff78-48db-a8a7-23f7542c343a loglevel=3"
}

menuentry "Windows" {
	icon /EFI/refind/next-theme/icons/os_win.png
	loader /EFI/Microsoft/Boot/bootmgfw.efi
}

menuentry "OSX" {
	icon /EFI/refind/next-theme/icons/os_mac.png
	loader /EFI/Apple/Boot/bootmgfw.efi
}
````

Entries that are autodetected should also show the proper icons.