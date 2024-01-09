 <img align="right" src="https://github.com/Icesito68/Port-Windows-11-Lg-G8x/blob/Lg-G8x/mh2lm.png" width="350" alt="Windows 11 Running On A Lg G8x">


# Windows en el Lg G8x

- Entra en el modo EDL y restaura el respaldo de tus particiones boot_a y boot_b

#### Arranca en TWRP del dispositivo

#### Desmonta todas las particiones
Ve a mount en TWRP y desmonta todas las particiones

## Pasar las herramientas necesarias:
```cmd
adb push parted /cache
```

## Iniciar ADB shell
```cmd
adb shell
```

# Restaurar particiones
#### Darle los permisos necesarios a la herramienta
```sh
chmod 755 /cache/parted
```


### Iniciar parted
```sh
./parted /dev/block/sda
```

### Borrar la partición `win` 
>Para asegurarte de que la partición 32 es win puedes usar
>  `print all`
```sh
rm 32
```

### Borrar la partición `esp` 
>Para asegurarte de que la partición 31 es esp puedes usar
>  `print all`
```sh
rm 31
```

### Redimensionar particion `userdata`
>Para asegurarte de que la partición 30 es userdata puedes usar
>  `print all`
```sh
resizepart 30
126GB
```

### Salir de parted
```sh
quit
```

### Reiniciar a TWRP

- Formatea data
Ve a Wipe en TWRP y presiona Format Data, 
después escribe `yes`.

### Comprueba si android inicia
Solo reinicia el teléfono y comprueba si Android inicia

## ¡Terminado!
