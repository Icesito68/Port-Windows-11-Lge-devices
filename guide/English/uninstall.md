 <img align="right" src="https://github.com/Icesito68/Port-Windows-11-Lg-G8x/blob/Lg-G8x/mh2lm.png" width="350" alt="Windows 11 Running On A Lg G8x">

# Running Windows on LG G8x

## Uninstalling Windows

### Prerequisites
- [ADB & Fastboot](https://developer.android.com/studio/releases/platform-tools)

- [Qfil](https://github.com/Icesito68/Port-Windows-11-Lge-devices/releases/tag/Qfil) (to restore partitions)
  
- [Parted script](https://github.com/Icesito68/Port-Windows-11-Lge-devices/releases/download/Scripts/parted)
  
- [TWRP](https://drive.google.com/file/d/1xc9DhNX5bj8PZKOZc09N5QhtOGamKD9o/view?usp=share_link) or [Orange Fox](https://drive.google.com/file/d/1EGyZOBfdfZ_4nAqD7FURbJ-Bvq3E4ckO/view?usp=share_link)
  
- Boot backups

#### Restore boot backups
> Go to EDL mode and use Qfil to restore your boot_a and boot_b backups

#### Boot TWRP on the device
> Use the Magisk module linked above if you don't already have it installed

#### Unmount all partitions
> Go to mount in TWRP and unmount all partitions

#### Run parted
> Put parted in your platform tools folder, then run
```cmd
adb push parted /cache && chmod 755 /cache/parted && /parted /dev/block/sda
```

#### Delete Windows Partition
> Use `print all` to make sure that partition 32 is Windows
```sh
rm 32
```

#### Delete ESP Partition
> Use `print all` to make sure that partition 31 is ESP
```sh
rm 31
```

#### Resize userdata Partition
> Use `print all` to make sure that partition 30 is userdata
```sh
resizepart 30
126GB
```

#### Exit Parted
```sh
quit
```

#### Format data
Go to the Wipe menu in TWRP and press Format Data, then type `yes`

#### Check if Android boots
Reboot your device and check if Android boots

## Finished!







