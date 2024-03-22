## Objetivo
Matryoshka dolls are a set of wooden dolls of decreasing size placed one inside another. What's the final one? Image: [this](https://mercury.picoctf.net/static/2978e1270538613cd8181c7b0dabe9bd/dolls.jpg)

## Pistas
- Wait, you can hide files inside files? But how do you find them?
- Make sure to submit the flag as picoCTF{XXXXX}

## Solución
```
┌──(kali㉿kali)-[~/Documents/Retos/matryoshka_doll]
└─$ ls
dolls.jpg
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/matryoshka_doll]
└─$ open dolls.jpg &
[1] 40807
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/matryoshka_doll]
└─$                                                                                                            1 ⚙
[1]  + done       open dolls.jpg
┌──(kali㉿kali)-[~/Documents/Retos/matryoshka_doll]
└─$ binwalk dolls.jpg                            

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 594 x 1104, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
272492        0x4286C         Zip archive data, at least v2.0 to extract, compressed size: 378942, uncompressed size: 383937, name: base_images/2_c.jpg
651600        0x9F150         End of Zip archive, footer length: 22

                                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/matryoshka_doll]
└─$ unzip  dolls.jpg                             
Archive:  dolls.jpg
warning [dolls.jpg]:  272492 extra bytes at beginning or within zipfile
  (attempting to process anyway)
  inflating: base_images/2_c.jpg     
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/matryoshka_doll]
└─$ ls                                                                                                         1 ⨯
base_images  dolls.jpg
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/matryoshka_doll]
└─$ cd base_images    
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/matryoshka_doll/base_images]
└─$ ls
2_c.jpg
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/matryoshka_doll/base_images]
└─$ open 2_c.jpg &  
[1] 41221
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/matryoshka_doll/base_images]
└─$                                                                                                            1 ⚙
[1]  + done       open 2_c.jpg
┌──(kali㉿kali)-[~/Documents/Retos/matryoshka_doll/base_images]
└─$ binwalk 2_c.jpg  

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 526 x 1106, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
187707        0x2DD3B         Zip archive data, at least v2.0 to extract, compressed size: 196042, uncompressed size: 201444, name: base_images/3_c.jpg
383804        0x5DB3C         End of Zip archive, footer length: 22
383915        0x5DBAB         End of Zip archive, footer length: 22

                                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/matryoshka_doll/base_images]
└─$ unzip 2_c.jpg   
Archive:  2_c.jpg
warning [2_c.jpg]:  187707 extra bytes at beginning or within zipfile
  (attempting to process anyway)
  inflating: base_images/3_c.jpg     
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/matryoshka_doll/base_images]
└─$ ls                                                                                                         1 ⨯
2_c.jpg  base_images
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/matryoshka_doll/base_images]
└─$ cd base_images 
                                                                                                                   
┌──(kali㉿kali)-[~/…/Retos/matryoshka_doll/base_images/base_images]
└─$ ls
3_c.jpg
                                                                                                                   
┌──(kali㉿kali)-[~/…/Retos/matryoshka_doll/base_images/base_images]
└─$ unzip 3_c.jpg 
Archive:  3_c.jpg
warning [3_c.jpg]:  123606 extra bytes at beginning or within zipfile
  (attempting to process anyway)
  inflating: base_images/4_c.jpg     
                                                                                                                   
┌──(kali㉿kali)-[~/…/Retos/matryoshka_doll/base_images/base_images]
└─$ ls                                                                                                         1 ⨯
3_c.jpg  base_images
                                                                                                                   
┌──(kali㉿kali)-[~/…/Retos/matryoshka_doll/base_images/base_images]
└─$ cd base_images 
                                                                                                                   
┌──(kali㉿kali)-[~/…/matryoshka_doll/base_images/base_images/base_images]
└─$ ls
4_c.jpg
                                                                                                                   
┌──(kali㉿kali)-[~/…/matryoshka_doll/base_images/base_images/base_images]
└─$ unzip 4_c.jpg 
Archive:  4_c.jpg
warning [4_c.jpg]:  79578 extra bytes at beginning or within zipfile
  (attempting to process anyway)
  inflating: flag.txt                
                                                                                                                   
┌──(kali㉿kali)-[~/…/matryoshka_doll/base_images/base_images/base_images]
└─$ ls                                                                                                         1 ⨯
4_c.jpg  flag.txt
                                                                                                                   
┌──(kali㉿kali)-[~/…/matryoshka_doll/base_images/base_images/base_images]
└─$ cat flag.txt                   
picoCTF{4cf7ac000c3fb0fa96fb92722ffb2a32}
```

## Notas adicionales


## Referencias

