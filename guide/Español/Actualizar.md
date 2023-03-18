#### con Qfil pon la imagen de Mass Storage Mode en boot_a y boot_b

> Cuando el Lg G8X sea detectado como disco

```cmd
diskpart
```


### Asigna `x` al volumen de Windows

#### Seleciona el volumen de Windows del teléfono
> use `list volume` to find it, it's usually the one before the last

```diskpart
select volume <number>
```

#### Agsigna la letra x
```diskpart
assign letter=x
```

### Salir de diskpart:
```diskpart
exit
```


# Instalar los Drivers

> reemplaza `<mh2lmdriversfolder>` por la localización de la carpeta de los drivers

> abre un cmd como administrador


```cmd
.\driverupdater.exe -d <mh2lmdriversfolder>\definitions\Desktop\ARM64\Internal\mh2lm.txt -r <mh2lmdriversfolder> -p X:
```


### Arranca con la imagen de aranque de Windows #####

  
  

# ¡Terminado!
