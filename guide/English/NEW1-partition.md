 <img align="right" src="https://github.com/Icesito68/Port-Windows-11-Lg-G8x/blob/Lg-G8x/mh2lm.png" width="350" alt="Windows 11 Running On A Lg G8x">


## Running Windows on the LG G8x

## Partitioning your device

### Prerequisites
- [ADB & Fastboot](https://developer.android.com/studio/releases/platform-tools)
  
- [Parted script]()
  
- [Recovery image]

### Notes
> [!WARNING]  
> All your data will be erased! Back up now if needed.
> 
> Do not run the same command twice unless specified.
>  
> Do not run all commands at once, execute them in order!
>
> YOU CAN BREAK YOUR DEVICE WITH THE COMMANDS BELOW IF YOU DO THEM WRONG!!!
>
> DO NOT REBOOT YOUR PHONE! If you think you made a mistake, ask for help in the [Telegram chat]([https://t.me/WinOnF1](https://t.me/winong8x)).

#### Boot TWRP 3.6.0 on the device


#### Unmount all partitions
Go to mount on TWRP and unmount all partitions

## Move parted to the device
```cmd
adb push parted /cache
```

## Start ADB shell
```cmd
adb shell
```

# Create partitions
#### Give parted necessary permissions
```sh
chmod 755 /cache/parted
```


### Start parted
```sh
./parted /dev/block/sda
```

### Delete the `grow` partition
>To make sure that partition 31 is grow you can use
>  `print all`
```sh
rm 31
```

### Resize the `userdata` partition
>To make sure that partition 30 is userdata you can use
>  `print all`
```sh
resizepart 30
```
>Replace XX with the amount of storage you want for Userdata, the rest will be for Windows
```sh
XXGB
```

### Create partitions
> If you get any warning message telling you to ignore or cancel, just type i and enter

#### For all models:

- Create the ESP partition (stores Windows bootloader data and EFI files)
>We want this partition to have 500MB, replace XX with the "END" of userdata
```sh
mkpart esp fat32 XXGB XX.5GB
```

- Create the main partition where Windows will be installed to
> Replace XX with the "END" of ESP, this storage will be for windows
```sh
mkpart win ntfs XX.5GB 126GB
```

### Exit parted
```sh
quit
```

### Reboot to TWRP

- Format Android data
Go to Wipe menu and press Format Data, then type `yes`.

### Check if Android still starts
Just reboot the phone and see if Android still boots.


## [Next step: Installing Windows](https://github.com/Icesito68/Port-Windows-11-Lg-G8x/blob/main/guide/English/2-Instalation.md)
