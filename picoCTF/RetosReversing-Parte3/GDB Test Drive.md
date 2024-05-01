## Objetivo
Can you get the flag?Download this [binary](https://artifacts.picoctf.net/c/85/gdbme).Here's the test drive instructions:

- `$ chmod +x gdbme`
- `$ gdb gdbme`
- `(gdb) layout asm`
- `(gdb) break *(main+99)`
- `(gdb) run`
- `(gdb) jump *(main+104)`

## Pistas


## Solución
```
elyahir-picoctf@webshell:~/gdb-test$ ls
gdbme
elyahir-picoctf@webshell:~/gdb-test$ chmod +x gdbme 
elyahir-picoctf@webshell:~/gdb-test$ gdb gdbme
GNU gdb (Ubuntu 12.1-0ubuntu1~22.04) 12.1
Copyright (C) 2022 Free Software Foundation, Inc.
License GPLv3+: GNU GPL version 3 or later <http://gnu.org/licenses/gpl.html>
This is free software: you are free to change and redistribute it.
There is NO WARRANTY, to the extent permitted by law.
Type "show copying" and "show warranty" for details.
This GDB was configured as "x86_64-linux-gnu".
Type "show configuration" for configuration details.
For bug reporting instructions, please see:
<https://www.gnu.org/software/gdb/bugs/>.
Find the GDB manual and other documentation resources online at:
    <http://www.gnu.org/software/gdb/documentation/>.

For help, type "help".
Type "apropos word" to search for commands related to "word"...
Reading symbols from gdbme...
(No debugging symbols found in gdbme)
(gdb) layout asm


DENTRO DEL LAYOUT
-----------------------------------------------------------------------------------
(gdb) break *(main+99)
Breakpoint 1 at 0x132a
(gdb) run
Starting program: /home/elyahir-picoctf/gdb-test/gdbme
warning: Error disabling address space randomization: Operation not permitted
[Thread debugging using libthread_db enabled]
Using host libthread_db library "/lib/x86_64-linux-gnu/libthread_db.so.1".

Breakpoint 1, 0x00005648f85b532a in main ()
(gbd) jump *(main+104)
Continuing at 0x5648f85b532f.
picoCTF{d3bugg3r_dr1v3_197c378a}
(gdb) ior 1 (process 301) exited normally]
-----------------------------------------------------------------------------------



Flag: picoCTF{d3bugg3r_dr1v3_197c378a}
```

## Notas adicionales


## Referencias

