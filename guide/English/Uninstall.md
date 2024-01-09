 <img align="right" src="https://github.com/Icesito68/Port-Windows-11-Lg-G8x/blob/Lg-G8x/mh2lm.png" width="350" alt="Windows 11 Running On A Lg G8x">


# Windows on Lg G8x

- Go to EDL mode and restore your boot_a and boot_b backups

#### Boot TWRP on the device

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

# Restore Partitions
#### Give parted necessary permissions
```sh
chmod 755 /cache/parted
```


### Start Parted
```sh
./parted /dev/block/sda
```

### Delete `win` Partition
>To make sure that partition 32 is win you can use 
>  `print all`
```sh
rm 32
```

### Delete `esp` Partition
>To make sure that partition 31 is esp you can use
>  `print all`
```sh
rm 31
```


### Resize `userdata` Partition
>To make sure that partition 31 is Userdata you can use
>  `print all`
```sh
resizepart 30
126GB
```

### Exit Parted
```sh
quit
```

### Reboot to TWRP

- Format data
Go to Wipe menu on TWRP and press Format Data, 
then write `yes`.

### Check if Android boots
Reboot your device and check if Android boots

## ¡Done!
