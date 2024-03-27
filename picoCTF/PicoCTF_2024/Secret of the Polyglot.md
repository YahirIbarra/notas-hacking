## Objetivo

The Network Operations Center (NOC) of your local institution picked up a suspicious file, they're getting conflicting information on what type of file it is. They've brought you in as an external expert to examine the file. Can you extract all the information from this strange file?Download the suspicious file [here](https://artifacts.picoctf.net/c_titan/96/flag2of2-final.pdf).
## Solución
```
Descargar el archivo
usar el comando open para abrirlo
copiar la parte de la bandera que esta ahí [1n_pn9_&_pdf_90974127}]
cerrar el archivo
con el comando file nos damos cuenta que en realidad es un archivo png
cambiamos la extension a png con mv
abrimos la imagen que se creó
copiamos la parte de la bandera que esta ahí [picoCTF{f1u3n7_]
flag: picoCTF{f1u3n7_1n_pn9_&_pdf_90974127}
```
## Notas adicionales

Cuando los archivos son binarios pueden representar diferentes cosas dependiendo de la extension.
## Referencias