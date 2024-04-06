## Objetivo
Download this image and find the flag.

- [Download image](https://artifacts.picoctf.net/c/217/pico.flag.png)

## Pistas
- We know the end sequence of the message will be `$t3g0`.

## Solución
```
┌──(kali㉿kali)-[~/…/Retos/segundo_parcial/forensic/stego]
└─$ ls
pico.flag.png
                                                                                                                   
┌──(kali㉿kali)-[~/…/Retos/segundo_parcial/forensic/stego]
└─$ open pico.flag.png                    
                                                                                                                   
┌──(kali㉿kali)-[~/…/Retos/segundo_parcial/forensic/stego]
└─$ file pico.flag.png  
pico.flag.png: PNG image data, 585 x 172, 8-bit/color RGBA, non-interlaced
                                                                                                                   
┌──(kali㉿kali)-[~/…/Retos/segundo_parcial/forensic/stego]
└─$ exiftool pico.flag.png                                                        
ExifTool Version Number         : 12.76
File Name                       : pico.flag.png
Directory                       : .
File Size                       : 13 kB
File Modification Date/Time     : 2023:08:04 16:36:21-04:00
File Access Date/Time           : 2024:04:05 23:37:00-04:00
File Inode Change Date/Time     : 2024:04:05 23:36:46-04:00
File Permissions                : -rw-r--r--
File Type                       : PNG
File Type Extension             : png
MIME Type                       : image/png
Image Width                     : 585
Image Height                    : 172
Bit Depth                       : 8
Color Type                      : RGB with Alpha
Compression                     : Deflate/Inflate
Filter                          : Adaptive
Interlace                       : Noninterlaced
Image Size                      : 585x172
Megapixels                      : 0.101
                                                                                                                   
┌──(kali㉿kali)-[~/…/Retos/segundo_parcial/forensic/stego]
└─$ strings pico.flag.png | grep picoCTf            
                                                                                                                   
┌──(kali㉿kali)-[~/…/Retos/segundo_parcial/forensic/stego]
└─$ zsteg pico.flag.png                                                                                        1 ⨯
b1,r,lsb,xy         .. text: "~__B>VG?G@"
b1,rgb,lsb,xy       .. text: "picoCTF{7h3r3_15_n0_5p00n_a9a181eb}$t3g0"
b1,abgr,lsb,xy      .. text: "E2A5q4E%uSA"
b2,b,lsb,xy         .. text: "AAPAAQTAAA"
b2,b,msb,xy         .. text: "HWUUUUUU"
b2,a,lsb,xy         .. file: Matlab v4 mat-file (little endian) >\004<\305P, numeric, rows 0, columns 0
b2,a,msb,xy         .. file: Matlab v4 mat-file (little endian) | <\243, numeric, rows 0, columns 0
b3,r,lsb,xy         .. file: gfxboot compiled html help file
b4,r,lsb,xy         .. file: Targa image data (16-273) 65536 x 4097 x 1 +4352 +4369 - 1-bit alpha - right "\021\020\001\001\021\021\001\001\021\021\001"                                                                              
b4,g,lsb,xy         .. file: 0420 Alliant virtual executable not stripped
b4,b,lsb,xy         .. file: Targa image data - Map 272 x 17 x 16 +257 +272 - 1-bit alpha "\020\001\021\001\021\020\020\001\020\001\020\001"                                                                                          
b4,bgr,lsb,xy       .. file: Targa image data - Map 273 x 272 x 16 +1 +4113 - 1-bit alpha "\020\001\001\001"
b4,rgba,lsb,xy      .. file: Novell LANalyzer capture file
b4,rgba,msb,xy      .. file: Applesoft BASIC program data, first line number 8
b4,abgr,lsb,xy      .. file: Novell LANalyzer capture file



Flag: picoCTF{7h3r3_15_n0_5p00n_a9a181eb}
```

## Notas adicionales


## Referencias

