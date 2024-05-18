## Objetivo
Can you figure out what is in the `eax` register at the end of the `main` function? Put your answer in the picoCTF flag format: `picoCTF{n}` where `n` is the contents of the `eax` register in the decimal number base. If the answer was `0x11` your flag would be `picoCTF{17}`.Debug [this](https://artifacts.picoctf.net/c/520/debugger0_b).

## Pistas
- You could calculate `eax` yourself, or you could set a breakpoint for after the calculcation and inspect `eax` to let the program do the heavy-lifting for you.

## Solución
```
┌──(kali㉿kali)-[~/Documents/Retos/tercer-parcial/gdb-baby-step-2]
└─$ ls                                                                                                          1 ⚙
debugger0_b
                                                                                                                    
┌──(kali㉿kali)-[~/Documents/Retos/tercer-parcial/gdb-baby-step-2]
└─$ file debugger0_b                                                                                            1 ⚙
debugger0_b: ELF 64-bit LSB executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, BuildID[sha1]=95b0203be2982e75dbc01d1cc25b1309f7aec5f7, for GNU/Linux 3.2.0, not stripped
                                                                                                                    
┌──(kali㉿kali)-[~/Documents/Retos/tercer-parcial/gdb-baby-step-2]
└─$ ghidra                                                                                                      1 ⚙
Picked up _JAVA_OPTIONS: -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true
Picked up _JAVA_OPTIONS: -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true


* DENTRO DE GHIDRA DECODIFICAMOS LA FUNCION MAIN Y OBTENEMOS EL SIGUIENTE CODIGO *
int main(void)


{
  int local_10;
  int local_c;
  
  local_c = 0x1e0da;
  for (local_10 = 0; local_10 < 0x25f; local_10 = local_10 + 1) {
    local_c = local_c + local_10;
  }
  return local_c;


* ESCRIBIMOS LA SOLUCION EN UN CODIGO DE C *


┌──(kali㉿kali)-[~/Documents/Retos/tercer-parcial/gdb-baby-step-2]
└─$ nano solution.c                                                                                             1 ⚙
                                                                                                                    
┌──(kali㉿kali)-[~/Documents/Retos/tercer-parcial/gdb-baby-step-2]
└─$ cat solution.c                                                                                              1 ⚙
#include<stdio.h>

int main(void)

{
  int local_10;
  int local_c;
  
  local_c = 0x1e0da;
  for (local_10 = 0; local_10 < 0x25f; local_10 = local_10 + 1) {
    local_c = local_c + local_10;
  }
  printf("%i", local_c);
  return 0;
}
                         1 ⨯ 1 ⚙
                                                                                                                    
┌──(kali㉿kali)-[~/Documents/Retos/tercer-parcial/gdb-baby-step-2]
└─$ sudo gcc solution.c -o solution                                                                             1 ⚙
                                                                                                                    
┌──(kali㉿kali)-[~/Documents/Retos/tercer-parcial/gdb-baby-step-2]
└─$ ls                                                                                                          1 ⚙
debugger0_b  solution  solution.c
                                                                                                                    
┌──(kali㉿kali)-[~/Documents/Retos/tercer-parcial/gdb-baby-step-2]
└─$ ./solution                                                                                                  1 ⚙
307019



Flag: picoCTF{307019}
```

## Notas adicionales


## Referencias

