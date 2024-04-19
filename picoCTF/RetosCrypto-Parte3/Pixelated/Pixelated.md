## Objetivo
I have these 2 images, can you make a flag out of them? [scrambled1.png](https://mercury.picoctf.net/static/49743139fb7c10765dbf462d40987d2a/scrambled1.png) [scrambled2.png](https://mercury.picoctf.net/static/49743139fb7c10765dbf462d40987d2a/scrambled2.png)

## Pistas
- [https://en.wikipedia.org/wiki/Visual_cryptography](https://en.wikipedia.org/wiki/Visual_cryptography)
- Think of different ways you can "stack" images

## Solución
```
┌──(kali㉿kali)-[~/Documents/Retos/pixelated]
└─$ ls
scrambled1.png  scrambled2.png
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/pixelated]
└─$ nano script.py
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/pixelated]
└─$ cat script.py
from PIL import Image
import numpy as np

imagen1 = np.asarray(Image.open("scrambled1.png"))
imagen2 = np.asarray(Image.open("scrambled2.png"))

datos = imagen1.copy() + imagen2.copy()

nueva = Image.fromarray(datos)

nueva.save("nueva.png", "PNG")
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/pixelated]
└─$ python3 script.py
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/pixelated]
└─$ ls
nueva.png  scrambled1.png  scrambled2.png  script.py
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/pixelated]
└─$ open nueva.png 


Flag: picoCTF{2a4d45c7}
```

## Notas adicionales


## Referencias

