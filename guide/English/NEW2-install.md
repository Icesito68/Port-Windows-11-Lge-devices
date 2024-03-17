<img align="right" src="https://github.com/Icesito68/Port-Windows-11-Lg-G8x/blob/Lg-G8x/mh2lm.png" width="350" alt="Windows 11 Running On To LG G8x">

## Running Windows on the Lg G8x

## Installing Windows

### Prerequisites
- [Windows on ARM image](https://worproject.com/esd)
  
- [UEFI image]()
  
- [Drivers](https://github.com/Icesito68/Port-Windows-11-Lge-devices/releases/download/Drivers/mh2lm.drivers.zip)
  
- [Msc script](https://github.com/Icesito68/Port-Windows-11-Lge-devices/releases/download/Scripts/msc.sh)

  
- [TWRP]() (should already be installed)


# Previous

- Make a backup of the Boot_a and Boot_b partitions with Qfil

- With Qfil, flash "LGG8XMassStorageBoot.img" in boot.
  
- Then exit EDL, so your PC will recognize the G8x as a disk

- If you have engineering abl_a you can instead go to fastboot and run
  ```sh
  fastboot boot LGG8XMassStorageBoot.img
  ```

# Format Esp and Win

> On windows explorer identify ESP, it should be called EFI and have about 500MB
> right click and fast format it as Fat32
> Same with Win, it shouldnt have a name but be about the amount of GB you chose
> right click and fast format it as NTFS
  

## Install

> replace `<path/to/Install.wim>` with the path of the install.wim file

> `install.wim` is in the sources folder of the ISO,
> you can get it after mounting or extracting the ISO

```cmd
dism /apply-image /ImageFile:<path/to/install.wim> /index:1 /ApplyDir:X:\
```
> replace `X` with the letter of your win partition


# Install the Drivers

> open a cmd as Administrator

> on cmd go to location of the drivers folder where `driverupdater.exe` is located

```cmd
.\driverupdater.exe -d .\definitions\Desktop\ARM64\Internal\mh2lm.txt -r . -p X:\
```
> replace `X` with the letter of your win partition

  

# Create the Windows bootloader files


```cmd
bcdboot X:\Windows /s Y: /f UEFI
```
>where X is win partition and Y is esp partition
  
  

# Allow unsigned drivers

> if you don't do this you will get a BSOD

```cmd
bcdedit /store Y:\EFI\Microsoft\BOOT\BCD /set {default} testsigning on
```
> where Y is esp partition


# Create ESP Flag 

> if you don't do this you windows will throw an error and cannot boot!

#### Boot TWRP


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

#### Give parted necessary permissions
```sh
chmod 755 /cache/parted
```


### Start parted
```sh
./parted /dev/block/sda
```
### Make ESP partiton bootable so the EFI image can detect it
```sh
set 30 esp on
```

### Exit parted
```sh
quit
```


# [We are almost done, now let's setup dualboot](/guide/English/dualboot.md)
















