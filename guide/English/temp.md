- [Mass storage boot image](https://github.com/Icesito68/Port-Windows-11-Lge-devices/releases/download/Files/LGG8XMassStorageBoot.img)
  
- [Qfil](https://github.com/Icesito68/Port-Windows-11-Lge-devices/releases/tag/Qfil)
  
### Boot to EDL
- Open **Device Manager** on your PC
- With the phone turned off, hold **volume down** + **power**.
- Keep holding as it displays the unlocked bootloader warning.
- After the screen turns dark, release the **power** button while continuing to hold the **volume down** button.
- While holding the **volume down** button, start rapidly pressing the **volume up** button.
- Keep doing this until you see **QDLoader 9008** or **QUSB_BULK** in the Device Manager on your PC.
- If the device has a ⚠️ yellow warning triangle, you need to install fastboot drivers before you can continue to the next step.

### Reboot to download mode
- Hold **volume down** + **power**.
- Keep holding as it displays the unlocked bootloader warning.
- After the screen turns dark, release the **power** button while continuing to hold the **volume up** button.
- While holding the **volume down** button, press the **volume up** button.

### Setting up Qfil
- Open **Qfil**.
- In "Select Build Type", select **flat build**.
- In "Select programmer", select the downloaded firehose.
- In Configuration, make sure the "Device Type" is set to **UFS**.

### Clearing the laf partition
- In **Qfil**, select Tools > Partition manager, and click **Ok**
- Right click on **laf_a** and press **read**. Then press **erase**.
- Do the same thing for **laf_b**
- 

### Setting up mass storage mode
```cmd
fastboot boot LGG8XMassStorageBoot.img
```








> [!Note]
> This will back up your **laf_a** and **laf_b** partitions to `C:\users\name\AppData\roaming\qualcomm\qfil\comportno\`















### Reboot to recovery
> Reboot to recovery. Reinstall the Magisk recovery module if needed.
























