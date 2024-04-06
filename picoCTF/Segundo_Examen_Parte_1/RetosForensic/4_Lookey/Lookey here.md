## Objetivo
Attackers have hidden information in a very large mass of data in the past, maybe they are still doing it.Download the data [here](https://artifacts.picoctf.net/c/126/anthem.flag.txt).

## Pistas
- Download the file and search for the flag based on the known prefix.

## Solución
```
┌──(kali㉿kali)-[~/…/Retos/segundo_parcial/forensic/lookey]
└─$ ls
anthem.flag.txt
                                                                                                                   
┌──(kali㉿kali)-[~/…/Retos/segundo_parcial/forensic/lookey]
└─$ cat anthem.flag.txt | grep picoCTF
      we think that the men of picoCTF{gr3p_15_@w3s0m3_2116b979}
```

## Notas adicionales


## Referencias

