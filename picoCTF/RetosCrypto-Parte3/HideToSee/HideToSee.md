## Objetivo
How about some hide and seek heh?Look at this image [here](https://artifacts.picoctf.net/c/239/atbash.jpg).

## Pistas
- Download the image and try to extract it.

## Solución
```
┌──(kali㉿kali)-[~/Documents/Retos/hidetosee]
└─$ ls
atbash.jpg
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/hidetosee]
└─$ file atbash.jpg     
atbash.jpg: JPEG image data, JFIF standard 1.01, aspect ratio, density 1x1, segment length 16, baseline, precision 8, 465x455, components 3
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/hidetosee]
└─$ steghide extract -sf atbash.jpg 
Enter passphrase: 
wrote extracted data to "encrypted.txt".
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/hidetosee]
└─$ ls
atbash.jpg  encrypted.txt
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/hidetosee]
└─$ cat encrypted.txt 
krxlXGU{zgyzhs_xizxp_1u84w779}



* ENTRAMOS A CyberChef Y PASAMOS EL TEXTO CON CIFRADO ATBASH *


Flag: picoCTF{atbash_crack_1f84d779}
```

## Notas adicionales


## Referencias
- https://gchq.github.io/CyberChef/#recipe=Atbash_Cipher()&input=Cg
