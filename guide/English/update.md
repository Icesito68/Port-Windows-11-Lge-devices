<img align="right" src="https://github.com/Icesito68/Port-Windows-11-Lg-G8x/blob/Lg-G8x/mh2lm.png" width="350" alt="Windows 11 Running On To LG G8x">

# Running Windows on the LG G8x

## Updating drivers

### Prerequisites
- [ADB & Fastboot](https://developer.android.com/studio/releases/platform-tools)
  
- [Drivers](https://github.com/Icesito68/Port-Windows-11-Lge-devices/releases/download/Drivers/mh2lm.drivers.zip)

- [Qfil](https://github.com/Icesito68/Port-Windows-11-Lge-devices/releases/tag/Qfil)

- [Mass storage boot image](https://github.com/Icesito68/Port-Windows-11-Lge-devices/releases/download/Files/LGG8XMassStorageBoot.img)

## Method 1: offline method
> This requires you to use a PC. Use Method 2 if you don't have one on hand.

### Reboot to download mode
- Hold **volume down** + **power**.
- Keep holding as it displays the unlocked bootloader warning.
- After the screen turns dark, release the **power** button while continuing to hold the **volume up** button.
- While holding the **volume down** button, press the **volume up** button.

#### Setting up mass storage mode
```cmd
fastboot boot LGG8XMassStorageBoot.img
```

### Diskpart
```cmd
diskpart
```

#### Select the phone's Windows volume
> Use `list volume` to find it, it should be named **WINMH2LM**
```diskpart
select volume <number>
```

#### Assign the letter x
```diskpart
assign letter x
```

#### Exit diskpart:
```diskpart
exit
```

### Installing Drivers
> Unpack the driver archive, then open the `OfflineUpdater.cmd` file

> Enter the drive letter of `Windows`, which should be X, then press enter

#### Reboot your device
> Once the drivers have finished installing

## Finished!

## Method 2: online method
> This does not require a PC, but may fail if driver signatures change

#### Installing drivers
> Download and extract the drivers archive onto your device, then run the `OnlineUpdater.cmd` file

#### Reboot your device
> Once the drivers have finished installing

## Finished!

















