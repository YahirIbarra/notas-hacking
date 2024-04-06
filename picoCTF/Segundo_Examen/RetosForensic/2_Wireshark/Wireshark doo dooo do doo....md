## Objetivo
Can you find the flag? [shark1.pcapng](https://mercury.picoctf.net/static/ae5b2bc07928fca272ff3900dc9a6cef/shark1.pcapng).

## Pistas


## Solución
```
┌──(kali㉿kali)-[~/…/Retos/segundo_parcial/forensic/wireshark]
└─$ ls
shark1.pcapng
                                                                                                                   
┌──(kali㉿kali)-[~/…/Retos/segundo_parcial/forensic/wireshark]
└─$ wireshark shark1.pcapng                                                               
20:29:33.095     Main Warn FIX Add drag reordering to UAT dialog


* Dentro de WireShark damos follow a los paquetes TCP
* En el stream 5 podemos encontrar la siguiente cadena "Gur synt vf cvpbPGS{c33xno00_1_f33_h_qrnqorrs}"
* Tras decodificar la cadena anterior con la codificacion ROT13 encontramos la bandera


Flag: The flag is picoCTF{p33kab00_1_s33_u_deadbeef}
```

## Notas adicionales


## Referencias
* https://gchq.github.io/CyberChef/#recipe=ROT13(true,true,false,13)&ieol=CRLF&oeol=CRLF
