## Objetivo
Sometimes you need to handle process data outside of a file. Can you find a way to keep the output from this program and search for the flag? Connect to `jupiter.challenges.picoctf.org 14291`.

## Pistas
- Remember the flag format is picoCTF{XXXX}
- What's a pipe? No not that kind of pipe... This [kind](http://www.linfo.org/pipes.html)

## Solución
```
elyahir-picoctf@webshell:~$ nc jupiter.challenges.picoctf.org 14291 | sort | uniq -c

   1988 Again, I really don't think this is a flag
   2071 I don't think this is a flag either
   3969 Not a flag either
   1972 This is defintely not a flag
      1 picoCTF{digital_plumb3r_ea8bfec7}
```

## Notas adicionales
- Los pipelines nos permiten ejecutar comandos posteriores a los comandos de la izquierda
- El comando sort nos permite ordenar un texto alfabeticamente
- El comando uniq -c nos permite contar la cantidad de lineas que se repiten

## Referencias

