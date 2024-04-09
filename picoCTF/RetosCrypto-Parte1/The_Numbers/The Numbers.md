## Objetivo
The [numbers](https://jupiter.challenges.picoctf.org/static/f209a32253affb6f547a585649ba4fda/the_numbers.png)... what do they mean?

## Pistas
- The flag is in the format PICOCTF{}

## Solución
```
┌──(kali㉿kali)-[~/Documents/Retos/the_numbers]
└─$ ls                  
the_numbers.png
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/the_numbers]
└─$ file the_numbers.png
the_numbers.png: PNG image data, 774 x 433, 8-bit/color RGB, non-interlaced
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/the_numbers]
└─$ open the_numbers.png
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/the_numbers]
└─$ echo "16 9 3 15 3 20 6 { 20 8 5 14 21 13 2 5 18 19 13 1 19 15 14 }"
16 9 3 15 3 20 6 { 20 8 5 14 21 13 2 5 18 19 13 1 19 15 14 }


* ENTRAR A CyberChef Y DECODIFICAR EL MENSAJE


┌──(kali㉿kali)-[~/Documents/Retos/the_numbers]
└─$ echo "picoctf{thenumbersmason}" | tr [a-z] [A-Z]                                                         130 ⨯
PICOCTF{THENUMBERSMASON}




Flag: PICOCTF{THENUMBERSMASON}
```

## Notas adicionales


## Referencias
- https://gchq.github.io/CyberChef/#recipe=A1Z26_Cipher_Decode('Space')
