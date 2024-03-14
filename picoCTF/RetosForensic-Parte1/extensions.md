## Objetivo
This is a really weird text file [TXT](https://jupiter.challenges.picoctf.org/static/e7e5d188621ee705ceeb0452525412ef/flag.txt)? Can you find the flag?

## Pistas
- How do operating systems know what kind of file it is? (It's not just the ending!
- Make sure to submit the flag as picoCTF{XXXXX}

## Solución
```
┌──(kali㉿kali)-[~/Documents/Retos/extensions]
└─$ file flag.txt 
flag.txt: PNG image data, 1697 x 608, 8-bit/color RGB, non-interlaced
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/extensions]
└─$ xxd -l 100  flag.txt            
00000000: 8950 4e47 0d0a 1a0a 0000 000d 4948 4452  .PNG........IHDR
00000010: 0000 06a1 0000 0260 0802 0000 0085 ad5e  .......`.......^
00000020: 9a00 0000 0173 5247 4200 aece 1ce9 0000  .....sRGB.......
00000030: 0004 6741 4d41 0000 b18f 0bfc 6105 0000  ..gAMA......a...
00000040: 0009 7048 5973 0000 1625 0000 1625 0149  ..pHYs...%...%.I
00000050: 5224 f000 0026 9549 4441 5478 5eed dd6b  R$...&.IDATx^..k
00000060: 421b 39b7                                B.9.
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/extensions]
└─$ mv flag.txt flag.png 
```

## Notas adicionales


## Referencias

