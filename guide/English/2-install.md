<img align="right" src="https://github.com/Icesito68/Port-Windows-11-Lg-G8x/blob/Lg-G8x/mh2lm.png" width="350" alt="Windows 11 Running On To LG G8x">

## Running Windows on the Lg G8x

## Installing Windows

### Prerequisites
- [Windows on ARM image](https://worproject.com/esd)
  
- [Drivers](https://github.com/Icesito68/Port-Windows-11-Lge-devices/releases/download/Drivers/mh2lm.drivers.zip)

- [Msc boot image](https://github.com/Icesito68/Port-Windows-11-Lge-devices/releases/download/Files/LGG8XMassStorageBoot.img)

## Setting up mass storage mode
> Make a backup of the Boot_a and Boot_b partitions with Qfil, then flash "LGG8XMassStorageBoot.img" in boot.

##### Enter msc mode
> Reboot to exit EDL, so your PC will recognize the G8x as a disk
>
> Or if you have engineering abl_a you can instead go to fastboot and run `fastboot boot LGG8XMassStorageBoot.img`

##### Formatting ESP
> In Windows Explorer (under My PC), identify ESP. It should be called EFI and be about 500MB.
> 
> Right click and fast format it as Fat32

##### Formatting ESP
> Do the same for Windows. It shouldn't have a name but the size should be similar to the size you chose Windows to be.
>
> Right click and fast format it as NTFS

## Installing Windows
> Replace `<path\to\install.esd>` with the actual path of install.esd (it may also be named install.wim)

```cmd
dism /apply-image /ImageFile:<path\to\install.esd> /index:6 /ApplyDir:X:\
```

> If you get `Error 87`, check the index of your image with `dism /get-imageinfo /ImageFile:<path\to\install.esd>`, then replace `index:6` with the actual index number of Windows 11 Pro in your image

##### Installing drivers
> Unpack the driver archive, then open the `OfflineUpdater.cmd` file

> Enter the drive letter of `Windows`, which should be X, then press enter
  
##### Create the Windows bootloader files
```cmd
bcdboot X:\Windows /s Y: /f UEFI
```

##### Allow unsigned drivers
> if you don't do this you will get a BSOD
```cmd
bcdedit /store Y:\EFI\Microsoft\BOOT\BCD /set "{default}" testsigning on
```

## Preparing to boot Windows

##### Reboot back to Android
Simply reboot your device

## [Last step: let's setup dualboot](dualboot.md)
















