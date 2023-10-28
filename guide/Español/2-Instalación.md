 <img align="right" src="https://github.com/Icesito68/Port-Windows-11-Lg-G8x/blob/Lg-V50/flashlmdd.png" width="350" alt="Windows 11 Running On A Lg G8x">


# Windows en el Lg V50

# Instalar Windows

# Previo

- Haz un backup de las particiones Boot_a y Boot_b con Qfil

- Con Qfil necesitas flashear en boot "LGG8XMassStorageBoot.img"
  
- Después sal de EDL, así tu PC reconocerá al G8x como un disco

## Asignar letras a los discos
  

#### Arranca diskpart en Windows

> Una vez que el G8x sea detectado como un disco

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

> abre un cmd como Administrador

> reemplaza `<mh2lmdriversfolder>` por la localización de la carpeta de drivers

```cmd
driverupdater.exe -d <mh2lmdriversfolder>\definitions\Desktop\ARM64\Internal\mh2lm.txt -r <mh2lmdriversfolder> -p X:
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



# [Ya casi hemos terminado, vamos a poner el dual boot](3-Dual-Boot.md)
