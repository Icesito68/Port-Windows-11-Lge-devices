 <img align="right" src="https://github.com/Icesito68/Port-Windows-11-Lg-G8x/blob/Lg-G8x/mh2lm.png" width="350" alt="Windows 11 Running On A Lg G8x">


## Running Windows on the LG G8x

## Partitioning your device

### Prerequisites
- [ADB & Fastboot](https://developer.android.com/studio/releases/platform-tools)

- [Qfil](https://github.com/Icesito68/Port-Windows-11-Lge-devices/releases/tag/Qfil) (to back up partitions)
  
- [Parted script](https://github.com/Icesito68/Port-Windows-11-Lge-devices/releases/download/Scripts/parted)
  
- [Recovery image]

### Notes
> [!WARNING]  
> All your data will be erased! Back up any data now if needed!
> 
> Do not run the same command twice unless specified.
>  
> Do not run all commands at once, execute them in order!
>
> YOU CAN BREAK YOUR DEVICE WITH THE COMMANDS BELOW IF YOU DO THEM WRONG!!!
>
> DO NOT REBOOT YOUR PHONE! If you think you made a mistake, ask for help in the [Telegram chat]([https://t.me/WinOnF1](https://t.me/winong8x)).

##### Flash TWRP 3.6.0
> Open a CMD window inside the platform-tools folder, then (while your phone is in fastboot mode) run
```cmd
fastboot flash recovery path\to\twrp.img reboot recovery
```

##### Unmount all partitions
Go to mount on TWRP and unmount all partitions

##### Preparing for partitioning
> Download the parted file and move it in the platform-tools folder, then run
```cmd
adb push parted /cache/ && adb shell "chmod 755 /cache/parted" && adb shell /cache/parted /dev/block/sda
```

##### Delete the `grow` partition
> To make sure that partition 31 is grow, run `print all`
```sh
rm 31
```

##### Resize the `userdata` partition
> To make sure that partition 30 is userdata, run `print all`
```sh
resizepart 30
```
> Replace XX with the amount of storage you want for userdata, the rest will be for Windows
```sh
XXGB
```

### Create partitions
> If you get any warning message telling you to ignore or cancel, just type i and enter

##### Creating the ESP partition
> We want this partition to have 500MB, replace XX with the "END" of userdata
```sh
mkpart esp fat32 XXGB XX.5GB
```

##### Making ESP bootable
> Replace "$" with your ESP partition number, usually 30 or 31
```cmd
set $ esp on
```

##### Creating the Windows partition
> Replace XX with the "END" of ESP, this storage will be for windows
```sh
mkpart win ntfs XX.5GB 126GB
```

##### Exit parted
```sh
quit
```

##### Format all data
Go to the Wipe menu in TWRP, press Format Data, then type `yes`.

##### Check if Android still starts
Just reboot the phone and see if Android still boots.

## [Next step: Installing Windows](2-install.md)












