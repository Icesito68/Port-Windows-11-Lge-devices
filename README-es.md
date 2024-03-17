 <img align="right" src="https://github.com/Icesito68/Port-Windows-11-Lg-G8x/blob/Lg-G8x/mh2lm.png" width="350" alt="Windows 11 Running On A Lg G8x">

# Windows en el Lg G8x 

## Idioma
[English](README.md) | **Español**

## ⚠️ Advertencia
No somos responsables de dispositivos bloqueados, particiones de recuperación eliminadas, trabajadores de xiaomi muertos,(Los de Lg están bien no se preocupen) tarjetas microSD muertas, pmics muertos, ram muertas, circuitos integrados muertos, cpus muertos, cualquier travesura de xiaomi/poco,(Lg no hace nada nunca) gatos o perros muertos, guerras nucleares o que te despidan porque olvidaste volver a iniciar Android para la alarma.

Este proyecto se encuentra en una etapa inicial, todos los archivos aquí han sido aportados por otros usuarios, aquí encontrará una guía con los archivos que logramos obtener. Este es un proceso delicado, hazlo bajo tu propio riesgo y sigue todos los pasos cuidadosamente.

**SI NO SE SIENTE CÓMODO MODIFICANDO SU TELÉFONO O SU TABLA DE PARTICIONES O ESTÁ PARANOICO DE BRICKEAR SU DISPOSITIVO SALGA AHORA MISMO!!! USTED HA SIDO ADVERTIDO, USTED ESTÁ POR SU CUENTA SI BCRICKEA SU DISPOSITIVO!!! ¡DE NUEVO! ¡¡¡USTED HA SIDO ADVERTIDO!!!**

<details>
<summary><a><strong>Requisitos Previos</strong></a></summary>

- ¡HACER UN BACKUP DE TODAS LAS PARTICIONES CON QFIL!

- Tener el bootloader desbloqueado

- Tener el [TWRP](https://drive.google.com/file/d/1xc9DhNX5bj8PZKOZc09N5QhtOGamKD9o/view?usp=share_link) u [Orange Fox](https://drive.google.com/file/d/1EGyZOBfdfZ_4nAqD7FURbJ-Bvq3E4ckO/view?usp=share_link) instalado (ambos se instalan como módulos de magisk)

- Tener descargadas las [Platform Tools](https://developer.android.com/studio/releases/platform-tools?hl=es-419)

- Tener un [ISO de Windows 11 Arm](https://uupdump.net/)

- Tener [Parted](https://www.mediafire.com/file/s9bjano4pezphou/parted/file) (Este archivo pertenece a [Gus33000](https://github.com/gus33000))

- Tener el script de [Mass Storage Mode](https://www.mediafire.com/file/m4yecbhu9fifjy7/msc.sh/file) (Este archivo pertenece a [Gus33000](https://github.com/gus33000)) o  Tener la imagen para entrar en [Mass Storage Mode](https://drive.google.com/file/d/13aqm-Hq4mWz5xDn9jSNxFSoF-qkEmUBx/view?usp=share_link) (gracias a Molly por compartirla)

- Tener la [Uefi del G8x](https://github.com/edk2-porting/edk2-msm/releases/tag/2302.1-mh2lm)
 
- Tener los [Drivers](https://github.com/Icesito68/LGE-SM8150-Drivers/releases/tag/2303.00) y el [Instalador](https://github.com/WOA-Project/DriverUpdater/releases/)

- [Qfil](https://drive.google.com/file/d/1P7uGjIirqGRdkwlxgKf_idepDlv6_u-q/view?usp=sharing) para los backups y flasheos necesarios

- [Drivers de Qfil](https://drive.google.com/file/d/1sPJm1RuSoVX9JMEs-Gx8xNuEDadO6rpj/view?usp=sharing) necesarios para que Qfil funcione 

- [Firehose para el g8x](https://drive.google.com/file/d/1ekI_d2-P9GdoakkSgk2hK1WHbQLIPlTQ/view?usp=sharing) necesario para que Qfil funcione

  </summary>
</details>

## Comencemos
- [Estado del proyecto](https://github.com/Icesito68/Port-Windows-11-Lg-G8x/blob/main/guide/Espa%C3%B1ol/Estado.md)
  
- [Instrucciones para instalar](https://github.com/Icesito68/Port-Windows-11-Lg-G8x/blob/main/guide/Espa%C3%B1ol/1-Particiones.md)

- [Instrucciones para desinstalar](https://github.com/Icesito68/Port-Windows-11-Lg-G8x/blob/main/guide/Espa%C3%B1ol/Desinstalar.md)


## Extras
- [Preparando el dual boot](guide/Español/dualboot-es.md)

- [Actualizar drivers](https://github.com/Icesito68/Port-Windows-11-Lg-G8x/blob/main/guide/Espa%C3%B1ol/Actualizar.md)

- [Extras](https://github.com/Icesito68/Port-Windows-11-Lg-G8x/blob/main/guide/Espa%C3%B1ol/Extra.md)

## Contribuidores
[<img alt="MollySophia" src="https://images.weserv.nl/?url=https://avatars.githubusercontent.com/u/20746884?v=4&w=45&fit=cover&mask=circle&maxage=7d" />](https://github.com/MollySophia)
[<img alt="Renegade Project Discord Members" src="https://images.weserv.nl/?url=https://cdn.discordapp.com/icons/736563593058713690/68f67bfddf4390b11effc99917b16338.webp?size=256&w=45&fit=cover&mask=circle&maxage=7d" />](https://discord.gg/XXBWfag)
[<img alt="gus33000" src="https://images.weserv.nl/?url=https://avatars.githubusercontent.com/u/3755345?v=4&w=45&fit=cover&mask=circle&maxage=7d" />](https://github.com/gus33000)
[<img alt="map220v" src="https://images.weserv.nl/?url=https://avatars.githubusercontent.com/u/14368485?v=4&w=45&fit=cover&mask=circle&maxage=7d" />](https://github.com/map220v)
[<img alt="Icesito68" src="https://images.weserv.nl/?url=https://avatars.githubusercontent.com/u/113939920?v=4&w=45&fit=cover&mask=circle&maxage=7d" />](https://github.com/Icesito68)
[<img alt="ArturoGC06" src="https://images.weserv.nl/?url=https://avatars.githubusercontent.com/u/76574534?v=4&w=45&fit=cover&mask=circle&maxage=7d" />](https://github.com/ArtturoGC06)



















- 







