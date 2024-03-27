## Objetivo

How about some hide and seek?Download this file [here](https://artifacts.picoctf.net/c_titan/128/unknown.zip).
## Solución

```
Descargar el archivo .zip
Descomprimirlo
usar exiftool para ver los metadatos de la imagen
desencriptar con base64 la cadena que aparece en la opcion Attribution URL.
flag: picoCTF{ME74D47A_HIDD3N_3b9209a2}
```
## Notas adicionales

**exiftool** nos ayuda a ver los metadatos de un archivo.
## Referencias