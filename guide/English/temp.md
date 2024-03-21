- [Mass storage boot image](https://github.com/Icesito68/Port-Windows-11-Lge-devices/releases/download/Files/LGG8XMassStorageBoot.img)
  
- [Qfil](https://github.com/Icesito68/Port-Windows-11-Lge-devices/releases/tag/Qfil)
  
### Boot to EDL
- Open **Device Manager** on your PC
- With the phone turned off, hold **volume down** + **power**.
- Keep holding as it displays the unlocked bootloader warning.
- After the screen turns dark, release the **power** button while continuing to hold the **volume up** button.
- While holding the **volume button**, start rapidly pressing the **volume up** button.
- Keep doing this until you see **QDLoader 9008** or **QUSB_BULK** in the Device Manager on your PC.
- If the device has a ⚠️ yellow warning triangle, you need to install fastboot drivers before you can continue to the next step.

### Clearing the laf partition
> Use Qfil to make a backup of the laf partition, then clear it

### Reboot to download mode
- Hold **volume down** + **power**.
- Keep holding as it displays the unlocked bootloader warning.
- After the screen turns dark, release the **power** button while continuing to hold the **volume up** button.
- While holding the **volume button**, press the **volume up** button.

### Setting up mass storage mode
```cmd
fastboot boot LGG8XMassStorageBoot.img
```
















### Reboot to recovery
> Reboot to recovery. Reinstall the Magisk recovery module if needed.
























