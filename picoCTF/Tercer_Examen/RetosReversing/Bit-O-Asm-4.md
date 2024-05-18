## Objetivo
Can you figure out what is in the `eax` register? Put your answer in the picoCTF flag format: `picoCTF{n}` where `n` is the contents of the `eax` register in the decimal number base. If the answer was `0x11` your flag would be `picoCTF{17}`.Download the assembly dump [here](https://artifacts.picoctf.net/c/511/disassembler-dump0_d.txt).

## Pistas
- Don't tell anyone I told you this, but you can solve this problem without understanding the compare/jump relationship.
- Of course, if you're really good, you'll only need one attempt to solve this problem.

## Solución
```
┌──(kali㉿kali)-[~/Documents/Retos/tercer-parcial/bit-o-asm-4]
└─$ ls
disassembler-dump0_d.txt
                                                                                                                    
┌──(kali㉿kali)-[~/Documents/Retos/tercer-parcial/bit-o-asm-4]
└─$ cat disassembler-dump0_d.txt 
<+0>:     endbr64 
<+4>:     push   rbp
<+5>:     mov    rbp,rsp
<+8>:     mov    DWORD PTR [rbp-0x14],edi
<+11>:    mov    QWORD PTR [rbp-0x20],rsi
<+15>:    mov    DWORD PTR [rbp-0x4],0x9fe1a
<+22>:    cmp    DWORD PTR [rbp-0x4],0x2710
<+29>:    jle    0x55555555514e <main+37>
<+31>:    sub    DWORD PTR [rbp-0x4],0x65
<+35>:    jmp    0x555555555152 <main+41>
<+37>:    add    DWORD PTR [rbp-0x4],0x65
<+41>:    mov    eax,DWORD PTR [rbp-0x4]
<+44>:    pop    rbp
<+45>:    ret


eax = 0x9fdb5
[rsi                      ] - 0x20
[edi                      ] - 0x14
[0x9fe1a - 0x65 = 0x9fdb5 ] - 0x4
[rpb                      ] <- rsp
[ret                      ]


┌──(kali㉿kali)-[~/Documents/Retos/tercer-parcial/bit-o-asm-4]
└─$ python3                                                                                                     1 ⚙
Python 3.9.8 (main, Nov  7 2021, 15:47:09) 
[GCC 11.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> 0x9fe1a <= 0x2710
False
>>> hex(0x9fe1a - 0x65)
'0x9fdb5'
>>> 0x9fdb5
654773


Flag: picoCTF{654773}
```

## Notas adicionales


## Referencias

