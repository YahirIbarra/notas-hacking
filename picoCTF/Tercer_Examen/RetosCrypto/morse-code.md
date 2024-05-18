## Objetivo
Morse code is well known. Can you decrypt this?Download the file [here](https://artifacts.picoctf.net/c/79/morse_chal.wav).Wrap your answer with picoCTF{}, put underscores in place of pauses, and use all lowercase.

## Pistas
- Audacity is a really good program to analyze morse code audio.

## Solución
```
┌──(kali㉿kali)-[~/Documents/Retos/tercer-parcial/morse-code]
└─$ ls
morse_chal.wav
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/tercer-parcial/morse-code]
└─$ file morse_chal.wav 
morse_chal.wav: RIFF (little-endian) data, WAVE audio, Microsoft PCM, 16 bit, mono 44100 Hz
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/tercer-parcial/morse-code]
└─$ audacity morse_chal.wav


* USANDO UN DECODIFICADOR ONLINE OBTENEMOS EL SIGUIENTE TEXTO *
* WH47 H47H 90D W20U9H7 *


┌──(kali㉿kali)-[~/Documents/Retos/tercer-parcial/morse-code]
└─$ python3
Python 3.9.8 (main, Nov  7 2021, 15:47:09) 
[GCC 11.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> a = "WH47 H47H 90D W20U9H7"
>>> a.lower().replace(" ", "_")
'wh47_h47h_90d_w20u9h7'


Flag: picoCTF{wh47_h47h_90d_w20u9h7}

```

## Notas adicionales


## Referencias
- https://morsecode.world/international/decoder/audio-decoder-adaptive.html
