## rEFInd Next theme

[rEFInd](http://www.rodsbooks.com/refind/) is a simplistic boot manager for UEFI
based systems. This is a clean and minimal theme for it.

> fork from [rEFInd Next](http://sdbinwiiexe.deviantart.com/)

![preview](https://user-images.githubusercontent.com/5492542/38356149-8c8f32d4-38f1-11e8-9d6b-1d4972fb72f4.png)

### Usage

To use this theme you'll want to clone it into the themes directory as your rEFInd
efi executable (usually `/boot/EFI/refind/themes`). Then you will want to add the following line to the end of your `refind.conf`:
```
include themes/next-theme/theme.conf
```

To make an icon appear when loading using graphical boot, open boot\_bg.png file in your image editor of choice, and just copy the operating system’s os\_icon over top of the background.  Then save the new image using the boot_ prefix.  A few examples have been included (windows, linux, ubuntu, linux mint, unknown)

To set the icons for your entries you will want to add the `icon` configuration
to each menuentry which points to the icon under `themes/next-theme/icons` that you
would like to use for that entry.

Here's an example configuration:

```
menuentry "Arch Linux" {
    icon /EFI/refind/themes/next-theme/icons/os_arch.png
    loader vmlinuz-linux
    initrd initramfs-linux.img
    options "ro root=UUID=dfb2919d-ff78-48db-a8a7-23f7542c343a loglevel=3"
}

menuentry "Windows" {
    icon /EFI/refind/themes/next-theme/icons/os_win.png
    loader /EFI/Microsoft/Boot/bootmgfw.efi
}

menuentry "OSX" {
    icon /EFI/refind/themes/next-theme/icons/os_mac.png
    loader /EFI/Apple/Boot/bootmgfw.efi
}
```

Entries that are autodetected should also show the proper icons.
