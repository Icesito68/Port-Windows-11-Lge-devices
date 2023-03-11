 <img align="right" src="https://github.com/Icesito68/Port-Windows-11-Lg-G8x/blob/main/mh2lm.png" width="350" alt="Windows 11 Running On A Lg G8x">


# Windows en el Lg G8x

#### Arranca en TWRP del dispositivo

#### Desmonta todas las particiones
Ve a mount en TWRP y desmonta todas las particiones

## Pasar las herramientas necesarias:
```cmd
adb push parted /sbin
```

## Iniciar ADB shell
```cmd
adb shell
```

# Crear particiones
#### Darle los permisos necesarios a la herramienta
```sh
chmod +x /sbin/*
```


### Iniciar parted
```sh
parted /dev/block/sda
```

### Borrar la partición `win` 
>Para asegurarte de que la partición 32 es win puedes usar
>  `print all`
```sh
rm 32
```

### Borrar la partición `grow` 
>Para asegurarte de que la partición 31 es grow puedes usar
>  `print all`
```sh
rm 31
```

### Borrar la partición `userdata` 
>Para asegurarte de que la partición 30 es userdata puedes usar
>  `print all`
```sh
rm 30
```

### Borrar la partición `grow` 
>Para asegurarte de que la partición 31 es grow puedes usar
>  `print all`
```sh
rm 31
```

### Borrar la partición `esp` 
>Para asegurarte de que la partición 29 es esp puedes usar
>  `print all`
```sh
rm 29
```
