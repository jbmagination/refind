# My rEFInd theme

[rEFInd](http://www.rodsbooks.com/refind/) is an easy to use boot manager for UEFI
based systems. This is my theme for it.

## Installation methods

### Manual 

 1. Download the zip file from the [releases page](https://github.com/jbmagination/refind-jbm/releases)

 2. Locate your refind EFI directory. This is commonly `/boot/EFI/refind`
    though it will depend on where you mount your ESP and where rEFInd is
    installed. `fdisk -l` and `mount` may help.

 3. Create a folder called `themes` inside it, if it doesn't already exist

 4. Extract the `refind-jbm` folder into the `themes` folder.

 5. To enable the theme add `include themes/refind-jbm/theme.conf` at the end of
    `refind.conf`.

### Automatic

```
bash <(wget -qO- https://jbmagination.com/refind/install)
```
Here's an example menuentry configuration:

```nginx
menuentry "Arch Linux" {
	icon /EFI/refind/themes/refind-jbm/icons/os_arch.png
	loader vmlinuz-linux
	initrd initramfs-linux.img
	options "rw root=UUID=dfb2919d-ff78-48db-a8a7-23f7542c343a loglevel=3"
}

menuentry "Windows" {
	icon /EFI/refind/themes/refind-jbm/icons/os_win.png
	loader /EFI/Microsoft/Boot/bootmgfw.efi
}

menuentry "OSX" {
	icon /EFI/refind/themes/refind-jbm/icons/os_mac.png
	loader /EFI/Apple/Boot/bootmgfw.efi
}
```

Entries that are autodetected should also show the proper icons.

### Background sizes

If you find the background looks blurry it may be due to the included wallpaper
being an incorrect resolution for your monitor. You can download the [original
high quality wallpaper](https://www.deviantart.com/leonardoalanb/art/Minimalist-wallpaper-295519786), resize it as appropriate, and replace the
`background.png`.

You can of course also choose your own background!

### Attribution

Windows icons and shutdown icon taken from rEFInd ambience theme

Everything else taken from rEFInd minimal theme
