## Objetivo
I wonder what this really is... [enc](https://mercury.picoctf.net/static/77a2b202236aa741e988581e78d277a6/enc) `''.join([chr((ord(flag[i]) << 8) + ord(flag[i + 1])) for i in range(0, len(flag), 2)])`

## Pistas
- You may find some decoders online

## Solución
```
──(kali㉿kali)-[~/Documents/Retos/tercer-parcial/transformation]
└─$ python3           
Python 3.9.8 (main, Nov  7 2021, 15:47:09) 
[GCC 11.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> enc = open("enc").read()
>>> print(enc)
灩捯䍔䙻ㄶ形楴獟楮獴㌴摟潦弸強㕤㐸㤸扽
>>> print(enc[0])
灩
>>> print(hex(ord(enc[0])))
0x7069
>>> for c in enc:
...     print(hex(ord(c)).lstrip("0x"), end='')
... 
7069636f4354467b31365f626974735f696e73743334645f6f665f385f37356434383938627d>>>

* ENTRAR A UN CONVERTIDOR DE HEXADECIMAL A ASCII *

Flag: picoCTF{16_bits_inst34d_of_8_75d4898b}
```

## Notas adicionales


## Referencias
- https://www.rapidtables.com/convert/number/hex-to-ascii.html
