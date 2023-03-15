 <img align="right" src="https://github.com/Icesito68/Port-Windows-11-Lg-G8x/blob/main/mh2lm.png" width="350" alt="Windows 11 Running On A Lg G8x">


# Windows on the Lg G8x

This steps are necesary to make the partitions where we are going to install Windows.

## Notes:
> **Warning** if you delete any partitions via diskpart later on or now windows will send a UFS command that gets misinterpreted which erase all your UFS.
- Ignore `udevadm` warnings.
- Don't run the same command twice
- DON'T REBOOT YOUR DEVICE if you think you made a mistake, ask for help in the [Telegram chat](https://t.me/winong8x)

#### Boot TWRP on the device


#### Unmount all partitions
Ve a mount en TWRP y desmonta todas las particiones

## Move parted to the device
```cmd
adb push parted /sbin
```

## Start ADB shell
```cmd
adb shell
```

# Create partitions
#### Give parted necessary permissions
```sh
chmod +x /sbin/*
```


### Start parted
```sh
parted /dev/block/sda
```

### Delete the `grow` partition
>To make sure that partition 31 is grow you can use
>  `print all`
```sh
rm 31
```

### Delete the `userdata` partition 
>To make sure that partition 30 is userdata you can use
>  `print all`
```sh
rm 30
```

### Create partitions
> If you get any warning message telling you to ignore or cancel, just type i and enter

#### For all models:

- Create the ESP partition (stores Windows bootloader data and EFI files)
```sh
mkpart esp fat32 19.1GB 19.5GB
```

- Create the main partition where Windows will be installed to
```sh
mkpart win ntfs 19.5GB 75.5GB
```

- Create the Android data partition
```sh
mkpart userdata ext4 75.5GB 126GB
```


### Make ESP partiton bootable so the EFI image can detect it
```sh
set 30 esp on
```

### Exit parted
```sh
quit
```

### Reboot to TWRP

### Start ADB shell again
```cmd
adb shell
```

### Format partitions
- Format the ESP partiton as FAT32
```sh
mkfs.fat -F32 -s1 /dev/block/by-name/esp
```

- Format the Windows partition as NTFS
```sh
mkfs.ntfs -f /dev/block/by-name/win
```

- Format Android data
Go to Wipe menu and press Format Data, then type `yes`.

### Check if Android still starts
Just reboot the phone and see if Android still boots.


## [Next step: Installing Windows](https://github.com/Icesito68/Port-Windows-11-Lg-G8x/blob/main/guide/English/2-Instalation.md)
