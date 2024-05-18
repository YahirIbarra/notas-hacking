## Objetivo
Can you figure out what is in the `eax` register? Put your answer in the picoCTF flag format: `picoCTF{n}` where `n` is the contents of the `eax` register in the decimal number base. If the answer was `0x11` your flag would be `picoCTF{17}`.Download the assembly dump [here](https://artifacts.picoctf.net/c/530/disassembler-dump0_c.txt).

## Pistas
- Not everything in this disassembly listing is optimal.

## Solución
```
┌──(kali㉿kali)-[~/Documents/Retos/tercer-parcial/bit-o-asm-3]
└─$ ls
disassembler-dump0_c.txt
                                                                                                                    
┌──(kali㉿kali)-[~/Documents/Retos/tercer-parcial/bit-o-asm-3]
└─$ cat disassembler-dump0_c.txt 
<+0>:     endbr64 
<+4>:     push   rbp
<+5>:     mov    rbp,rsp
<+8>:     mov    DWORD PTR [rbp-0x14],edi
<+11>:    mov    QWORD PTR [rbp-0x20],rsi
<+15>:    mov    DWORD PTR [rbp-0xc],0x9fe1a
<+22>:    mov    DWORD PTR [rbp-0x8],0x4
<+29>:    mov    eax,DWORD PTR [rbp-0xc]
<+32>:    imul   eax,DWORD PTR [rbp-0x8]
<+36>:    add    eax,0x1f5
<+41>:    mov    DWORD PTR [rbp-0x4],eax
<+44>:    mov    eax,DWORD PTR [rbp-0x4]
<+47>:    pop    rbp
<+48>:    ret


eax = 0x9fe1a * 0x4 = 0x27f868 + 0x1f5 = 0x27fa5d

[rsi     ] - 0x20
[edi     ] - 0x14
[0x9fe1a ] - 0xc
[0x4     ] - 0x8
[0x27fa5d] - 0x4
[rbp     ] <- rsp
[ret     ]
[        ] + 0x4


┌──(kali㉿kali)-[~/Documents/Retos/tercer-parcial/bit-o-asm-4]
└─$ python3                                                                                                     1 ⚙
Python 3.9.8 (main, Nov  7 2021, 15:47:09) 
[GCC 11.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> hex(0x9fe1a * 0x4)
'0x27f868'
>>> hex(0x27f868 + 0x1f5)
'0x27fa5d'
>>> 0x27fa5d
2619997



Flag: picoCTF{2619997}
```

## Notas adicionales


## Referencias

