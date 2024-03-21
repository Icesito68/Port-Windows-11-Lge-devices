 <img align="right" src="https://github.com/Icesito68/Port-Windows-11-Lg-G8x/blob/Lg-G8x/mh2lm.png" width="350" alt="Windows 11 Running On A Lg G8x">


# Running Windows on the LG G8x

## Partitioning your device

### Prerequisites
- [ADB & Fastboot](https://developer.android.com/studio/releases/platform-tools)

- [Qfil](https://github.com/Icesito68/Port-Windows-11-Lge-devices/releases/tag/Qfil) (to back up partitions)
  
- [Parted script](https://github.com/Icesito68/Port-Windows-11-Lge-devices/releases/download/Scripts/parted)
  
- [TWRP or Orange Fox](https://github.com/Icesito68/Port-Windows-11-Lge-devices/releases/tag/Recoveries)

### Notes
> [!WARNING]  
> 
> Do not run the same command twice unless specified.
>  
> Do not run all commands at once, execute them in order!
>
> YOU CAN BREAK YOUR DEVICE WITH THE COMMANDS BELOW IF YOU DO THEM WRONG!!!
>
> DO NOT REBOOT YOUR PHONE! If you think you made a mistake, ask for help in the [Telegram chat]([https://t.me/WinOnF1](https://t.me/winong8x)).

### Backing up partitions
> If you don't do this and mess something up, you're on your own

#### Boot to EDL
- Open **Device Manager** on your PC
- With the phone turned off, hold **volume down** + **power**.
- Keep holding as it displays the unlocked bootloader warning.
- After the screen turns dark, release the **power** button while continuing to hold the **volume down** button.
- While holding the **volume down** button, start rapidly pressing the **volume up** button.
- Keep doing this until you see **QDLoader 9008** or **QUSB_BULK** in the Device Manager on your PC.
- If the device has a ⚠️ yellow warning triangle, you need to install fastboot drivers before you can continue to the next step.

#### Reboot to download mode
- Hold **volume down** + **power**.
- Keep holding as it displays the unlocked bootloader warning.
- After the screen turns dark, release the **power** button while continuing to hold the **volume up** button.
- While holding the **volume down** button, press the **volume up** button.

#### Setting up Qfil
- Open **Qfil**.
- In "Select Build Type", select **flat build**.
- In "Select programmer", select the downloaded firehose.
- In Configuration, make sure the "Device Type" is set to **UFS**.

#### Backing up your partitions
- In **Qfil**, select Tools > Partition manager, and click **Ok**.
- Right click on **laf_a** and press **Read Data**.
- Do the same thing for **laf_b**, **boot_a**, **boot_b**, **abl_a**, **abl_b**, **aop_a**, **aop_b**, **xbl_a**, **xbl_b**, **ftc**, **fsg**, **fsc**, **modemst1**, **modemst2**, **modem_a**, **modem_b**

> [!Note]
> This will back up your partitions to `C:\users\name\AppData\roaming\qualcomm\qfil\comportno\`. You can restore them later with the **Load Image** function.

#### Clearing the laf partition
- In **Qfil**, select Tools > Partition manager, and click **Ok**.
- Right click on **laf_a** and press **Erase**.
- Do the same thing for **laf_b**

#### Reboot your phone
> Hold **power** to reboot back to Android

#### Flash TWRP or Orange Fox
> Use the provided files and flash them in Magisk, then reboot to recovery
>
> If you have Lineage recovery, you can also use that instead

#### Unmount all partitions
Go to mount in TWRP/Orange Fox and unmount all partitions

#### Preparing for partitioning
> Download the parted file and move it in the platform-tools folder, then run
```cmd
adb push parted /cache/ && adb shell "chmod 755 /cache/parted" && adb shell /cache/parted /dev/block/sda
```

#### Delete the `grow` partition
> To make sure that partition 31 is grow, run `print all`
```sh
rm 31
```

#### Resize the `userdata` partition
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

#### Creating the ESP partition
> We want this partition to have 500MB, replace XX with the "END" of userdata
```sh
mkpart esp fat32 XXGB XX.5GB
```

#### Creating the Windows partition
> Replace XX with the "END" of ESP, this storage will be for windows
```sh
mkpart win ntfs XX.5GB 126GB
```

#### Exit parted
```sh
quit
```

#### Format all data
Go to the Wipe menu in TWRP, press Format Data, then type `yes`.

#### Check if Android still starts
Just reboot the phone and see if Android still boots.

## [Next step: Installing Windows](2-install.md)












