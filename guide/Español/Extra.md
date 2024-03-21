<img align="right" src="https://github.com/Icesito68/Port-Windows-11-Lg-G8x/blob/Lg-G8x/mh2lm.png" width="350" alt="Windows 11 Ejecutándose en un LG G8x">

# Ejecutando Windows en LG G8x

### Lista de aplicaciones/juegos compatibles
Esta lista no pretende ser exhaustiva, simplemente enumera las aplicaciones/juegos que han sido probados por la comunidad
[El enlace se puede encontrar aquí](https://docs.google.com/spreadsheets/d/1XYuoySgYQE0HL573sA-0RGMX7I4lt5rWJuQ8Z8yRJNY/edit?usp=drivesdk)

También puedes encontrar una lista de software ARM dedicado [en este enlace](https://armrepo.ver.lt/)

#### ¡Finalizado!

### Alternar el modo de host USB
> [!Advertencia]
> Desactiva el modo de host USB si usas un concentrador USB con alimentación, ya que esto puede dañar irreversiblemente tu dispositivo. Si no usas un concentrador USB con alimentación, habilita el modo de host USB o no podrás usar ningún dispositivo USB.

Ejecuta [Control de Modo de Host USB](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/USBHost/USB.Host.Mode.Control.V4.0.vbs) para habilitar/deshabilitar el modo de host USB, confirma que deseas deshabilitar/habilitar el modo de host USB y luego confirma el reinicio

#### ¡Finalizado!

### Ocultar la unidad D (partición de módem)
> [!NOTA]
> Esto se recomienda porque esta unidad no debe modificarse, aunque algunas aplicaciones pueden intentar escribir en ella

- Abre una ventana de símbolo del sistema y ejecuta ```diskpart```
- Ejecuta ```list volume``` para ver todos los volúmenes disponibles
- Selecciona el disco que tiene la letra D con ```select volume $```, reemplazando "$" con el número de volumen
- Elimina la letra con ```remove letter d```
- Sal de diskpart con ```exit```

#### ¡Finalizado!

### Instalar Microsoft Office / Microsoft 365
- Descarga este [archivo ISO](https://mega.nz/file/hjAiSL4T#G7kOKpsUFpyL2UW9RQmY2e96urcQW5xZKdc7ciaNOy8) en la tableta
- Haz clic derecho en el archivo iso y selecciona Montar para abrirlo en el explorador
- Haz doble clic en ```Office Tool Plus.exe``` para iniciar el asistente de instalación
- En la ventana que aparece, haz clic en `Sí`
- Espera a que se complete la instalación

#### ¡Finalizado!

### Activar Windows / Office
Sigue las instrucciones de Massgravel [aquí](https://github.com/massgravel/Microsoft-Activation-Scripts)

#### ¡Finalizado!
