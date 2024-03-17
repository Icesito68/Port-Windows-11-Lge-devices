<img align="right" src="https://github.com/Icesito68/Port-Windows-11-Lg-G8x/blob/Lg-G8x/mh2lm.png" width="350" alt="Windows 11 Running On To LG G8x">

## Running Windows on the LG G8x

## Updating drivers

### Prerequisites
- [ADB & Fastboot](https://developer.android.com/studio/releases/platform-tools)
  
- [Drivers](https://github.com/Icesito68/Port-Windows-11-Lge-devices/releases/download/Drivers/mh2lm.drivers.zip)

- [Msc boot image](https://github.com/Icesito68/Port-Windows-11-Lge-devices/releases/download/Files/LGG8XMassStorageBoot.img)

## Method 1: offline method
> This requires you to use a PC

## Setting up mass storage mode
> Make a backup of the Boot_a and Boot_b partitions with Qfil, then flash "LGG8XMassStorageBoot.img" in boot.

##### Enter msc mode
> Reboot to exit EDL, so your PC will recognize the G8x as a disk
>
> Or if you have engineering abl_a you can instead go to fastboot and run `fastboot boot LGG8XMassStorageBoot.img`

## Diskpart
```cmd
diskpart
```

##### Select the phone's Windows volume
> Use `list volume` to find it, it's usually the one before the last
```diskpart
select volume <number>
```

##### Assign the letter x
```diskpart
assign letter x
```

##### Exit diskpart:
```diskpart
exit
```

## Installing Drivers


  

## Method 2: online method
> This does not require a PC, but may fail if driver signatures change

##### Installing drivers
> Download and extract the drivers archibe onto your device, then run the `OnlineUpdater.cmd` file

## Finished!

















