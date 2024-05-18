## Objetivo
This program has constructed the flag using hex ascii values. Identify the flag text by disassembling the program.You can download the file from [here](https://artifacts.picoctf.net/c/508/asciiftw).

## Pistas
- The combined range of hex-ascii for English alphabets and numerical digits is from 30 to 7A.
- Online hex-ascii converters can be helpful.

## Solución
```
* SI VEMOS EL TIPO DE ARCHIVO PODEMOS VER QUE ES UN BINARIO *

┌──(kali㉿kali)-[~/Documents/Retos/tercer-parcial/ascii-ftw]
└─$ file asciiftw 
asciiftw: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, BuildID[sha1]=e1c32dace8ac1516160b771e493f5ebffcac9855, for GNU/Linux 3.2.0, not stripped

* DESPUES LO ABRIMOS CON GHIDRA Y PODEMOS VER LA FUNCION MAIN *


        00101184 c6 45 d0 70     MOV        byte ptr [RBP + local_38],0x70
        00101188 c6 45 d1 69     MOV        byte ptr [RBP + local_37],0x69
        0010118c c6 45 d2 63     MOV        byte ptr [RBP + local_36],0x63
        00101190 c6 45 d3 6f     MOV        byte ptr [RBP + local_35],0x6f
        00101194 c6 45 d4 43     MOV        byte ptr [RBP + local_34],0x43
        00101198 c6 45 d5 54     MOV        byte ptr [RBP + local_33],0x54
        0010119c c6 45 d6 46     MOV        byte ptr [RBP + local_32],0x46
        001011a0 c6 45 d7 7b     MOV        byte ptr [RBP + local_31],0x7b
        001011a4 c6 45 d8 41     MOV        byte ptr [RBP + local_30],0x41
        001011a8 c6 45 d9 53     MOV        byte ptr [RBP + local_2f],0x53
        001011ac c6 45 da 43     MOV        byte ptr [RBP + local_2e],0x43
        001011b0 c6 45 db 49     MOV        byte ptr [RBP + local_2d],0x49
        001011b4 c6 45 dc 49     MOV        byte ptr [RBP + local_2c],0x49
        001011b8 c6 45 dd 5f     MOV        byte ptr [RBP + local_2b],0x5f
        001011bc c6 45 de 49     MOV        byte ptr [RBP + local_2a],0x49
        001011c0 c6 45 df 53     MOV        byte ptr [RBP + local_29],0x53
        001011c4 c6 45 e0 5f     MOV        byte ptr [RBP + local_28],0x5f
        001011c8 c6 45 e1 45     MOV        byte ptr [RBP + local_27],0x45
        001011cc c6 45 e2 41     MOV        byte ptr [RBP + local_26],0x41
        001011d0 c6 45 e3 53     MOV        byte ptr [RBP + local_25],0x53
        001011d4 c6 45 e4 59     MOV        byte ptr [RBP + local_24],0x59
        001011d8 c6 45 e5 5f     MOV        byte ptr [RBP + local_23],0x5f
        001011dc c6 45 e6 38     MOV        byte ptr [RBP + local_22],0x38
        001011e0 c6 45 e7 39     MOV        byte ptr [RBP + local_21],0x39
        001011e4 c6 45 e8 36     MOV        byte ptr [RBP + local_20],0x36
        001011e8 c6 45 e9 30     MOV        byte ptr [RBP + local_1f],0x30
        001011ec c6 45 ea 46     MOV        byte ptr [RBP + local_1e],0x46
        001011f0 c6 45 eb 30     MOV        byte ptr [RBP + local_1d],0x30
        001011f4 c6 45 ec 41     MOV        byte ptr [RBP + local_1c],0x41
        001011f8 c6 45 ed 46     MOV        byte ptr [RBP + local_1b],0x46
        001011fc c6 45 ee 7d     MOV        byte ptr [RBP + local_1a],0x7d
        00101200 0f b6 45 d0     MOVZX      EAX,byte ptr [RBP + local_38]
        00101204 0f be c0        MOVSX      EAX,AL
        00101207 89 c6           MOV        ESI,EAX
        00101209 48 8d 3d        LEA        RDI,[s_The_flag_starts_with_%x_00102004]         = "The flag starts with %x\n"
                 f4 0d 00 00
        00101210 b8 00 00        MOV        EAX,0x0
                 00 00
        00101215 e8 56 fe        CALL       <EXTERNAL>::printf                               int printf(char * __format, ...)
                 ff ff
        0010121a 90              NOP
        0010121b 48 8b 45 f8     MOV        RAX,qword ptr [RBP + local_10]
        0010121f 64 48 33        XOR        RAX,qword ptr FS:[0x28]
                 04 25 28 
                 00 00 00
        00101228 74 05           JZ         LAB_0010122f
        0010122a e8 31 fe        CALL       <EXTERNAL>::__stack_chk_fail                     undefined __stack_chk_fail()
                 ff ff
                             -- Flow Override: CALL_RETURN (CALL_TERMINATOR)


* AL DECOMPILARLA PODEMOS VER QUE DICE QUE LA BANDERA INICIA CON 0x70 *

  printf("The flag starts with %x\n",0x70);
  if (lVar1 != *(long *)(in_FS_OFFSET + 0x28)) {
    __stack_chk_fail();

* COPIAMOS LAS VARIABLES QUE SE GUARDAN EN LOS REGISTROS *

0x70
0x69
0x63
0x6f
0x43
0x54
0x46
0x7b
0x41
0x53
0x43
0x49
0x49
0x5f
0x49
0x53
0x5f
0x45
0x41
0x53
0x59
0x5f
0x38
0x39
0x36
0x30
0x46
0x30
0x41
0x46
0x7d

* LE DAMOS FORMATO HEXADECIMAL *

7069636f4354467b41534349495f49535f454153595f38393630463041467d

* CONVERTIMOS DE HEXADECIMAL A ASCII *

Flag: picoCTF{ASCII_IS_EASY_8960F0AF}
```

## Notas adicionales


## Referencias
- https://www.rapidtables.com/convert/number/hex-to-ascii.html
