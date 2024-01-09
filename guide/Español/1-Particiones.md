 <img align="right" src="https://github.com/Icesito68/Port-Windows-11-Lg-G8x/blob/Lg-G8x/mh2lm.png" width="350" alt="Windows 11 Running On A Lg G8x">


# Windows en el Lg G8x

Estos pasos son necesarios para crear las particiones donde pondremos Windows

## Notas:
> **Advertencia** si eliminas alguna partición via diskpart más adelante o ahora, Windows enviará un comando ufs que se malinterpretará y borrará toda la ufs
- Estos comandos han sido testeados.
- Ignora las advertencias de `udevadm`
- No ejecutes el mismo comando dos veces
- NO REINICIES TU DISPOSITIVO si crees que cometiste un error, preguntanos en el [Chat de Telegram](https://t.me/winong8x)

#### Arranca en el TWRP del dispositivo


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

# Crear particiones
#### Darle los permisos necesarios a la herramienta
```sh
chmod 775 /cache/parted
```


### Iniciar parted
```sh
./parted /dev/block/sda
```

### Borrar la partición `grow` 
>Para asegurarte de que la partición 31 es grow puedes usar
>  `print all`
```sh
rm 31
```

### Redimensionar la partición `userdata` 
>Para asegurarte de que la partición 30 es Userdata puedes usar
>  `print all`
```sh
resizepart 30
```
>Reemplaza XX con la cantidad de almacenamiento que quieras para Userdata, el resto se usara ora Windows
```sh
XXGB
```

### Crear particiones
> Si recibes cualquier advertencia que te diga ignorar o cancelar, solo escribe i y dale a enter enter

#### Para todos los modelos:

- Crea la partición ESP (Aqui estará el bootloader de Windows y los archivos EFI)
>Necesitamos que esta particion tenga 500MB, reemplaza XX con lo que diga "END" en Userdata
```sh
mkpart esp fat32 XXGB XX.5GB
```

- Creamos la partición principal donde instalaremos Windows
> Reemplazamos XX con lo que diga "END" en ESP
```sh
mkpart win ntfs XX.5GB 126GB
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


- Formatea data
Ve a Wipe en TWRP y presiona Format Data, 
después escribe `yes`.

### Comprueba si android inicia
Solo reinicia el teléfono y comprueba si Android inicia


## [Siguiente paso: Instalar Windows](https://github.com/Icesito68/Port-Windows-11-Lg-G8x/blob/main/guide/Espa%C3%B1ol/2-Instalaci%C3%B3n.md)
