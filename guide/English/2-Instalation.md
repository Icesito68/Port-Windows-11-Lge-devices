<img align="right" src="https://github.com/Icesito68/Port-Windows-11-Lg-G8x/blob/main/mh2lm.png" width="350" alt="Windows 11 Running On To LG G8x">


# Windows on the Lg G8x

# Install Windows

# Previous

- Make a backup of the Boot_a and Boot_b partitions with Qfil

- With Qfil you need to flash in boot "LGG8XMassStorageBoot.img"
  
- Then exit EDL, so your PC will recognize the G8x as a disk

## Assign drive letters
  

#### Start the Windows disk manager

> When the G8x is detected as a disk

```cmd
diskpart
```


### Assign letter `x` to Windows volume

#### Select the phone's Windows volume
> use `list volume` to find it, usually it's the penultimate one

```diskpart
select volume <number>
```

#### Assign the letter x
```diskpart
assign letter=x
```

### Assign `y` to esp volume

#### Select phone esp volume
> use `list volume` to find it, usually it's the last one

```diskpart
select volume <number>
```

#### Assign letter y

```diskpart
assign letter=y
```

### Exit diskpart:
```diskpart
exit
```

  
  

## Install

> replace `<path/to/Install.wim>` with the path of the install.wim file

> `install.wim` is in the sources folder of the ISO
> you can get it after mounting or extracting the ISO

```cmd
dism /apply-image /ImageFile:<path/to/install.wim> /index:1 /ApplyDir:X:\
```


# Install the Drivers

> replace `<mh2lmdriversfolder>` with the location of the drivers folder

> open a cmd as Administrator

```cmd
driverupdater.exe -d <mh2lmdriversfolder>\definitions\Desktop\ARM64\Internal\mh2lm.txt -r <mh2lmdriversfolder> -p X:
```

  

# Create the Windows bootloader files

```cmd
bcdboot X:\Windows /s Y: /f UEFI
```

  
  

# Allow unsigned drivers

> if you don't do this you will get a BSOD

```cmd
bcdedit /store Y:\EFI\Microsoft\BOOT\BCD /set {default} testsigning on
```

# Boot into Windows
> I recommend having a microSD on which you store the boot images

> so you don't need a pc to pass the files.

### Move `<uefi.img>` to the device

```cmd
adb push <uefi.img> /sdcard
```

##### if you have a micro sd use this

```cmd
adb push <uefi.img> /external_sd
```

# [We are almost done, let's put the dual boot](https://github.com/Icesito68/Port-Windows-11-Lg-G8x/blob/main/guide/English/3-Dual-Boot.md )
