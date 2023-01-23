# Instalar Windows
> Necesitas tener el  MTP desactivado en Mount

## Pasar las herramientas necesarias:
```cmd
adb push msc.sh /sbin
```

### Ejecutar el script

```cmd
adb shell sh /sbin/msc.sh
```

  

## Asignar letras a los discos
  

#### Arranca el administrador de discos de Windows

> Cuando el X3 Pro sea detectado como un disco

```cmd
diskpart
```


### Asignar letra `x` al volumen de Windows

#### Selecciona el volumen de Windows del Teléfono
> usa `list volume` para encontrarlo, normalmente es el penúltimo

```diskpart
select volume <number>
```

#### Assign the letter x
```diskpart
assign letter=x
```

### Asinar `y` al volumen de esp 

#### Selecciona el volumen de esp del teléfono
> usa `list volume` para encontrarlo, normalmente es el último

```diskpart
select volume <number>
```

#### Asignar letra y

```diskpart
assign letter=y
```

### Salir de diskpart:
```diskpart
exit
```

  
  

## Instalar

> reemplaza `<path/to/Install.wim>` por la ruta del archivo install.wim

> `install.wim` está en la carpeta sources de la ISO
> lo puedes obtener tras montar o extraer la ISO

```cmd
dism /apply-image /ImageFile:<path/to/install.wim> /index:1 /ApplyDir:X:\
```


# Instalar los Drivers

> reemplaza `<mh2lmdriversfolder>` por la localización de la carpeta de drivers

> abre un cmd como Administrador

```cmd
driverupdater.exe -d <mh2lmdriversfolder>\definitions\Desktop\ARM64\Internal\vayu.txt -r <mh2lmdriversfolder> -p X:
```

  

# Crear los archivos del bootloader de Windows 

```cmd
bcdboot X:\Windows /s Y: /f UEFI
```

  
  

# Permite los drivers no firmados

> si no haces esto obtendrás un BSOD

```cmd
bcdedit /store Y:\EFI\Microsoft\BOOT\BCD /set {default} testsigning on
```

# Arrancar en Windows
> Recomiendo tener una microSD en la que almacene las imágenes de arranque

> para que no necesites una pc para pasar los archivos.

### Mueve `<uefi.img>` al dispositivo

```cmd
adb push <uefi.img> /sdcard
```

##### si tienes una micro sd usa este

```cmd
adb push <uefi.img> /external_sd
```


### haz un backup de tu imagen de arranque actual
> solo tienes que hacer esto una vez

> ponla en tu micro sd si es posible


### Flashea la imagen uefi desde twrp.
ve hasta la `uefi.img` y flashea en boot.

# volver a Android
> usa tu backup de boot image desde twrp.

# ¡Terminado!
