## Objetivo
We found this [file](https://jupiter.challenges.picoctf.org/static/ab30fcb7d47364b4190a7d3d40edb551/mystery). Recover the flag.

## Pistas
- Try fixing the file header

## Solución
```
┌──(kali㉿kali)-[~/Documents/Retos/c0rrupt]
└─$ ls
mystery
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/c0rrupt]
└─$ file mystery      
mystery: data
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/c0rrupt]
└─$ xxd -l 100  mystery 
00000000: 8965 4e34 0d0a b0aa 0000 000d 4322 4452  .eN4........C"DR
00000010: 0000 066a 0000 0447 0802 0000 007c 8bab  ...j...G.....|..
00000020: 7800 0000 0173 5247 4200 aece 1ce9 0000  x....sRGB.......
00000030: 0004 6741 4d41 0000 b18f 0bfc 6105 0000  ..gAMA......a...
00000040: 0009 7048 5973 aa00 1625 0000 1625 0149  ..pHYs...%...%.I
00000050: 5224 f0aa aaff a5ab 4445 5478 5eec bd3f  R$......DETx^..?
00000060: 8e64 cd71                                .d.q
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/c0rrupt]
└─$ hexeditor mystery
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/c0rrupt]
└─$ pngcheck mystery 
zlib warning:  different version (expected 1.2.13, using 1.2.11)

mystery:  invalid chunk name "C"DR" (43 22 44 52)
ERROR: mystery
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/c0rrupt]
└─$ hexeditor mystery                                                                                          2 ⨯
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/c0rrupt]
└─$ hexeditor mystery
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/c0rrupt]
└─$ pngcheck mystery 
zlib warning:  different version (expected 1.2.13, using 1.2.11)

mystery  CRC error in chunk pHYs (computed 38d82c82, expected 495224f0)
ERROR: mystery
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/c0rrupt]
└─$ hexeditor mystery                                                                                          2 ⨯
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/c0rrupt]
└─$ pngcheck mystery 
zlib warning:  different version (expected 1.2.13, using 1.2.11)

mystery  invalid chunk length (too large)
ERROR: mystery
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/c0rrupt]
└─$ hexeditor mystery                                                                                          2 ⨯
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/c0rrupt]
└─$ pngcheck mystery 
zlib warning:  different version (expected 1.2.13, using 1.2.11)

mystery  invalid chunk length (too large)
ERROR: mystery
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/c0rrupt]
└─$ hexeditor mystery                                                                                          2 ⨯
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/c0rrupt]
└─$ pngcheck mystery 
zlib warning:  different version (expected 1.2.13, using 1.2.11)

OK: mystery (1642x1095, 24-bit RGB, non-interlaced, 96.3%).
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/c0rrupt]
└─$ xxd -l 100  mystery
00000000: 8950 4e47 0d0a 1a0a 0000 000d 4948 4452  .PNG........IHDR
00000010: 0000 066a 0000 0447 0802 0000 007c 8bab  ...j...G.....|..
00000020: 7800 0000 0173 5247 4200 aece 1ce9 0000  x....sRGB.......
00000030: 0004 6741 4d41 0000 b18f 0bfc 6105 0000  ..gAMA......a...
00000040: 0009 7048 5973 0000 1625 0000 1625 0149  ..pHYs...%...%.I
00000050: 5224 f000 00ff a549 4441 5478 5eec bd3f  R$.....IDATx^..?
00000060: 8e64 cd71
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/c0rrupt]
└─$ open mystery 

Flag: picoCTF{c0rrupt10n_1847995}
```

## Notas adicionales
- Todo formato de archivo posee diferentes bits de encabezado llamados Magic Bytes

## Referencias
- https://en.wikipedia.org/wiki/List_of_file_signatures
- https://en.wikipedia.org/wiki/PNG
- https://www.w3.org/TR/png/#11pHYs
