# rEFInd Regular Dark

[rEFInd](http://www.rodsbooks.com/refind/) is an easy to use boot manager for UEFI
based systems and this is a simplistic clean and minimal theme.

>This forked theme is modified dark version of [refind-theme-regular](https://github.com/bobafetthotmail/refind-theme-regular) by [bobafetthotmail](https://github.com/bobafetthotmail).
>>The original theme was [refind-theme-regular](https://github.com/munlik/refind-theme-regular) by [munlik](https://github.com/munlik).

![rEFInd-Regular-Dark](https://raw.githubusercontent.com/iammrmehedi/rEFInd-Regular-Dark/main/screenshot.webp)

## Installation

Fork this repo to you local directory by running the following command in terminal.

```bash
git clone https://github.com/iammrmehedi/rEFInd-Regular-Dark.git
```

## Usage

 1. Locate your refind EFI directory. This is commonly `/boot/EFI/refind`
    though it will depend on where you mount your ESP and where rEFInd is
    installed. `fdisk -l` and `mount` may help.

 2. Create a folder called `themes` inside it, if it doesn't already exist

 3. Clone this repository into the `themes` directory.

 4. To enable the theme add the following line at the end of `refind.conf`.

 ```text
include themes/rEFInd-Regular-Dark/theme.conf
 ```

 Here's an example menuentry configuration (from the screenshot)

```text
menuentry "Windows_11" {
   icon /EFI/refind/themes/rEFInd-Regular-Dark/icons/os_win11.png
   loader /EFI/Microsoft/Boot/bootmgfw.efi
}

menuentry "Debian" {
    icon /EFI/refind/themes/rEFInd-Regular-Dark/icons/os_debian.png
    volume 53f60ca1-c118-4885-b66b-3f29039e5a43
    loader /boot/vmlinuz-6.1.0-9-amd64
    initrd /boot/initrd.img-6.1.0-9-amd64
    options "root=UUID=60ebb4c2-e9e3-4ba4-a0a8-f662d51d8b4d ro quiet nomodeset mitigations=off "
}
```

Entries that are autodetected should also show the proper icons.
