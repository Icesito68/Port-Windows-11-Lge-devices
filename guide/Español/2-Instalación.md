 <img align="right" src="https://github.com/Icesito68/Port-Windows-11-Lg-G8x/blob/Lg-G8x/mh2lm.png" width="350" alt="Windows 11 Running On A Lg G8x">


# Windows en el Lg G8x

# Instalar Windows

# Previo

- Haz un backup de las particiones Boot_a y Boot_b con Qfil

- Con Qfil necesitas flashear en boot "LGG8XMassStorageBoot.img"
  
- Después sal de EDL, así tu PC reconocerá al G8x como un disco

- como alternative, si tienes abl_a de ingenieria puedes ejecutar en fastboot lo siguiente
  ```sh
  fastboot boot LGG8XMassStorageBoot.img
  ```

# Formatear esp y win

> identifica esp en el explorador de Windows, podria llamarse EFI y tener alrededor de 500MB

> dale click derecho y formato rapido en fat32

> lo mismo con win, podria no tener nombre pero tendra alrededor de la cantidad de GB que le pusiste anteriormente

> dale click derecho y formato rapido en ntfs

## Instalar

> reemplaza `<path/to/Install.wim>` por la ruta del archivo install.wim

> `install.wim` está en la carpeta sources de la ISO
> lo puedes obtener tras montar o extraer la ISO

```cmd
dism /apply-image /ImageFile:<path/to/install.wim> /index:1 /ApplyDir:X:\
```
> reemplaza `X` con la letra de tu particion win


# Instalar los Drivers

> abre un cmd como Administrador

> en cmd ve a la ruta de la carpeta drivers, donde `driverupdater.exe` se encuentra

```cmd
.\driverupdater.exe -d .\definitions\Desktop\ARM64\Internal\mh2lm.txt -r . -p X:\
```
> replace `X` with the letter of your win partition
  

# Crear los archivos del bootloader de Windows 

```cmd
bcdboot X:\Windows /s Y: /f UEFI
```
>reemplaza `X` con la letra particion win y `Y` con la letra de la particion esp

  
  

# Permite los drivers no firmados

> si no haces esto obtendrás un BSOD

```cmd
bcdedit /store Y:\EFI\Microsoft\BOOT\BCD /set {default} testsigning on
```
> reemplaza `Y` con la letra de la particion esp



# Crear Flag ESP  

> Si no haces esto, Windows no continuara con la instalacion!

#### Arranque a TWRP


#### Desmonta todas las particiones
Ve a mount en TWRP y desmonta todas las particiones

## Mueve Parted al dispositivo
```cmd
adb push parted /cache
```

## Inicia ADB shell
```cmd
adb shell
```

#### Dale los permisos necesarios a Parted
```sh
chmod 755 /cache/parted
```


### Inicia parted
```sh
./parted /dev/block/sda
```
### Vuelve la particion ESP booteable para que la imagen EFI pueda encontrarla
```sh
set 30 esp on
```

### Sal de parted
```sh
quit
```




# [Ya casi hemos terminado, vamos a poner el dual boot](https://github.com/Icesito68/Port-Windows-11-Lg-G8x/blob/main/guide/Espa%C3%B1ol/3-Dual-Boot.md)
