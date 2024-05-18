## Objetivo
Can you figure out what is in the `eax` register? Put your answer in the picoCTF flag format: `picoCTF{n}` where `n` is the contents of the `eax` register in the decimal number base. If the answer was `0x11` your flag would be `picoCTF{17}`.Download the assembly dump [here](https://artifacts.picoctf.net/c/510/disassembler-dump0_b.txt).

## Pistas
- `PTR`'s or 'pointers', reference a location in memory where values can be stored.

## Solución
```
┌──(kali㉿kali)-[~/Documents/Retos/tercer-parcial/bit-o-asm-2]
└─$ ls
disassembler-dump0_b.txt
                                                                                                                    
┌──(kali㉿kali)-[~/Documents/Retos/tercer-parcial/bit-o-asm-2]
└─$ cat disassembler-dump0_b.txt 
<+0>:     endbr64 
<+4>:     push   rbp
<+5>:     mov    rbp,rsp
<+8>:     mov    DWORD PTR [rbp-0x14],edi
<+11>:    mov    QWORD PTR [rbp-0x20],rsi
<+15>:    mov    DWORD PTR [rbp-0x4],0x9fe1a
<+22>:    mov    eax,DWORD PTR [rbp-0x4]
<+25>:    pop    rbp
<+26>:    ret
                                                                                                                    
┌──(kali㉿kali)-[~/Documents/Retos/tercer-parcial/bit-o-asm-2]
└─$ 
                                                                                                                    
┌──(kali㉿kali)-[~/Documents/Retos/tercer-parcial/bit-o-asm-2]
└─$ python3                                                                                                   130 ⨯
Python 3.9.8 (main, Nov  7 2021, 15:47:09) 
[GCC 11.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> 0x9fe1a
654874


Flag: picoCTF{654874}
```

## Notas adicionales


## Referencias

