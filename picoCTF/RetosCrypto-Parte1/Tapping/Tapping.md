## Objetivo
Theres tapping coming in from the wires. What's it saying `nc jupiter.challenges.picoctf.org 9422`.

## Pistas
- What kind of encoding uses dashes and dots?
- The flag is in the format PICOCTF{}

## Solución
```
┌──(kali㉿kali)-[~/Documents/Retos/tapping]
└─$ nc jupiter.challenges.picoctf.org 9422 
.--. .. -.-. --- -.-. - ..-. { -- ----- .-. ... ...-- -.-. ----- -.. ...-- .---- ... ..-. ..- -. ..--- -.... ---.. ...-- ---.. ..--- ....- -.... .---- ----- }


* ENTRAMOS A CyberChef Y DECODIFICAMOS EL CODIGO MORSE


Flag: PICOCTF{M0RS3C0D31SFUN2683824610}
```

## Notas adicionales


## Referencias
- https://gchq.github.io/CyberChef/#recipe=From_Morse_Code('Space','Line%20feed')&input=Li0tLiAuLiAtLi0uIC0tLSAtLi0uIC0gLi4tLiB7IC0tIC0tLS0tIC4tLiAuLi4gLi4uLS0gLS4tLiAtLS0tLSAtLi4gLi4uLS0gLi0tLS0gLi4uIC4uLS4gLi4tIC0uIC4uLS0tIC0uLi4uIC0tLS4uIC4uLi0tIC0tLS4uIC4uLS0tIC4uLi4tIC0uLi4uIC4tLS0tIC0tLS0tIH0g
