- [Msc boot image](https://github.com/Icesito68/Port-Windows-11-Lge-devices/releases/download/Files/LGG8XMassStorageBoot.img)
  
- [Qfil](https://github.com/Icesito68/Port-Windows-11-Lge-devices/releases/tag/Qfil)
  
### Boot to EDL
> Turn off your phone, then hold **volume down + power**. Keep holding while it displays the unlocked bootloader warning.

> After this warning the screen will turn dark. Release the power button (keep holding the volume down button!), and start rapidly pressing the **volume up** button like your life depends on it, until you see QDLoader 9008 in the Device Manager on your PC

### Setting up mass storage mode
> Make a backup of the Boot_a and Boot_b partitions with Qfil, then flash "LGG8XMassStorageBoot.img" into boot.

### Reboot to recovery
> Reboot to recovery. Reinstall the Magisk recovery module if needed.

#### Enter msc mode
> Reboot to exit EDL, so your PC will recognize the G8x as a disk

> Or if you have engineering abl_a you can instead go to fastboot and run `fastboot boot LGG8XMassStorageBoot.img`
























