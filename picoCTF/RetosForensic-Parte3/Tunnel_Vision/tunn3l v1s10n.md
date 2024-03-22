## Objetivo
We found this [file](https://mercury.picoctf.net/static/01be2b38ba97802285a451b94505ea75/tunn3l_v1s10n). Recover the flag.

## Pistas
- Weird that it won't display right...

## Solución
```
┌──(kali㉿kali)-[~/Documents/Retos/tunnel_vision]
└─$ ls
tunn3l_v1s10n
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/tunnel_vision]
└─$ file tunn3l_v1s10n
tunn3l_v1s10n: data
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/tunnel_vision]
└─$ xxd -l 100  tunn3l_v1s10n
00000000: 424d 8e26 2c00 0000 0000 bad0 0000 bad0  BM.&,...........
00000010: 0000 6e04 0000 3201 0000 0100 1800 0000  ..n...2.........
00000020: 0000 5826 2c00 2516 0000 2516 0000 0000  ..X&,.%...%.....
00000030: 0000 0000 0000 231a 1727 1e1b 2920 1d2a  ......#..'..) .*
00000040: 211e 261d 1a31 2825 352c 2933 2a27 382f  !.&..1(%5,)3*'8/
00000050: 2c2f 2623 332a 262d 2420 3b32 2e32 2925  ,/&#3*&-$ ;2.2)%
00000060: 3027 2333                                0'#3
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/tunnel_vision]
└─$ hexeditor tunn3l_v1s10n 
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/tunnel_vision]
└─$ exiftool tunn3l_v1s10n                                                                                     1 ⨯
ExifTool Version Number         : 12.76
File Name                       : tunn3l_v1s10n
Directory                       : .
File Size                       : 2.9 MB
File Modification Date/Time     : 2024:03:21 17:02:41-04:00
File Access Date/Time           : 2024:03:21 17:02:41-04:00
File Inode Change Date/Time     : 2024:03:21 17:02:41-04:00
File Permissions                : -rw-r--r--
File Type                       : BMP
File Type Extension             : bmp
MIME Type                       : image/bmp
BMP Version                     : Windows V3
Image Width                     : 1134
Image Height                    : 306
Planes                          : 1
Bit Depth                       : 24
Compression                     : None
Image Length                    : 2893400
Pixels Per Meter X              : 5669
Pixels Per Meter Y              : 5669
Num Colors                      : Use BitDepth
Num Important Colors            : All
Image Size                      : 1134x306
Megapixels                      : 0.347
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/tunnel_vision]
└─$ open tunn3l_v1s10n 
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/tunnel_vision]
└─$ Gtk-Message: 17:03:30.058: Failed to load module "gail"

** (gimp-2.10:46261): WARNING **: 17:03:30.080: (../atk-adaptor/bridge.c:1018):atk_bridge_adaptor_init: runtime check failed: (root)

                                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/tunnel_vision]
└─$ hexeditor tunn3l_v1s10n 
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/tunnel_vision]
└─$ open tunn3l_v1s10n     
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/tunnel_vision]
└─$ Gtk-Message: 17:04:41.732: Failed to load module "gail"

** (gimp-2.10:46639): WARNING **: 17:04:41.760: (../atk-adaptor/bridge.c:1018):atk_bridge_adaptor_init: runtime check failed: (root)


Flag: picoCTF{qu1t3_a_v13w_2020}
```

## Notas adicionales


## Referencias
- https://en.wikipedia.org/wiki/BMP_file_format
