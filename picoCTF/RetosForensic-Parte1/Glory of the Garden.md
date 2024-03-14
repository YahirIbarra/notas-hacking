## Objetivo
This [garden](https://jupiter.challenges.picoctf.org/static/d0e1ffb10fc0017c6a82c57900f3ffe3/garden.jpg) contains more than it seems.

## Pistas
- What is a hex editor?

## Solución
```
┌──(kali㉿kali)-[~/Documents/Retos]
└─$ strings -n 10 garden.jpg | grep picoCTF
Here is a flag "picoCTF{more_than_m33ts_the_3y3eBdBd2cc}"
```

## Notas adicionales
- Podemos usar el hexeditor de kali para revisar los bites
- Al presionar ctrl+W podemos buscar una cadena de texto dentro del hexadecimal
- Tambien podemos usar strings para buscar la misma cadena dentro del hexadecimal

## Referencias

