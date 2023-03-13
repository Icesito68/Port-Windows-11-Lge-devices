 <img align="right" src="https://github.com/Icesito68/Port-Windows-11-Lg-G8x/blob/main/mh2lm.png" width="350" alt="Windows 11 Running On A Lg G8x">


# Windows en el Lg G8x

Estos pasos son necesarios para crear las particiones donde pondremos Windows

## Notas:
> **Advertencia** si eliminas alguna partición via diskpart más adelante o ahora, Windows enviará un comando ufs que se malinterpretará y borrará toda la ufs
- Estos comandos han sido testeados.
- Ignora las advertencias de `udevadm`
- No ejecutes el mismo comando dos veces
- NO REINICIES TU DISPOSITIVO si crees que cometiste un error, preguntanos en el [Chat de Telegram](https://t.me/winong8x)

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

### Crear particiones
> Si recibes cualquier advertencia que te diga ignorar o cancelar, solo escribe i y dale a enter enter

#### Para todos los modelos:

- Crea la partición ESP (Aqui estará el bootloader de Windows y los archivos EFI)
```sh
mkpart esp fat32 19.1GB 19.5GB
```

- Creamos la partición principal donde instalaremos Windows
```sh
mkpart win ntfs 19.5GB 75.5GB
```

- Creamos la partición de datos de Android
```sh
mkpart userdata ext4 75.5GB 126GB
```


### Hace a ESP la partición de arranque para que la imagen EFI pueda detectarla
```sh
set 30 esp on
```

### Salir de parted
```sh
quit
```

### Reiniciar a TWRP

### Iniciar shell otra vez en tu PC
```cmd
adb shell
```

### Formatear las particiones
-  Formatea la partición ESP en FAT32
```sh
mkfs.fat -F32 -s1 /dev/block/by-name/esp
```

-  Formatea la partición de Windows en NTFS
```sh
mkfs.ntfs -f /dev/block/by-name/win
```

- Formatea data
Ve a Wipe en TWRP y presiona Format Data, 
después escribe `yes`.

### Comprueba si android inicia
Solo reinicia el teléfono y comprueba si Android inicia


## [Siguiente paso: Instalar Windows](https://github.com/Icesito68/Port-Windows-11-Lg-G8x/blob/main/guide/English/2-Instalation.md)
