#### with Qfil put Mass Storage Mode image in boot_a and boot_b

> When the Lg G8X is detected as disk

```cmd
diskpart
```


### Assign `x` to the Windows volume

#### Select the phone's Windows volume
> use `list volume` to find it, it's usually the one before the last

```diskpart
select volume <number>
```

#### Assign the letter x
```diskpart
assign letter=x
```

### Exit diskpart:
```diskpart
exit
```


# Install the Drivers

> replace `<mh2lmdriversfolder>` with the location of the drivers folder

> open a cmd as administrator


```cmd
.\driveupdater.exe -d <mh2lmdriversfolder>\definitions\Desktop\ARM64\Internal\mh2lm.txt -r <mh2lmdriversfolder> -p X:
```


### Boot with the Windows boot image #####

  
  

# Finished!
