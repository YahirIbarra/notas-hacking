## Objetivo
A second message has come in the mail, and it seems almost identical to the first one. Maybe the same thing will work again.Download the message [here](https://artifacts.picoctf.net/c/182/message.txt).

## Pistas
- Try a frequency attack
- Do the punctuation and the individual words help you make any substitutions?

## Solución
```
┌──(kali㉿kali)-[~/Documents/Retos/tercer-parcial/substitution1]
└─$ ls
message.txt
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/tercer-parcial/substitution1]
└─$ cat message.txt           
SYTe (eakdy tkd sjbyndr yar thjm) jdr j yobr kt skxbnyrd ersndzyo skxbryzyzkc. Skcyreyjcye jdr bdrercyrq gzya j ery kt sajhhrcmre gazsa yrey yarzd sdrjyzwzyo, yrsaczsjh (jcq mkkmhzcm) evzhhe, jcq bdklhrx-ekhwzcm jlzhzyo. Sajhhrcmre nenjhho skwrd j cnxlrd kt sjyrmkdzre, jcq garc ekhwrq, rjsa ozrhqe j eydzcm (sjhhrq j thjm) gazsa ze enlxzyyrq yk jc kchzcr eskdzcm erdwzsr. SYTe jdr j mdrjy gjo yk hrjdc j gzqr jddjo kt skxbnyrd ersndzyo evzhhe zc j ejtr, hrmjh rcwzdkcxrcy, jcq jdr akeyrq jcq bhjorq lo xjco ersndzyo mdknbe jdkncq yar gkdhq tkd tnc jcq bdjsyzsr. Tkd yaze bdklhrx, yar thjm ze: bzskSYT{TD3UN3CSO_4774SV5_4D3_S001_7JJ384LS}


* ENTRAMOS A UN DECODIFICADOR DE SUBSTITUCION Y OBTENEMOS LO SIGUIENTE *


CTFs (short for capture the flag) are a type of computer security competition. Contestants are presented with a set of challenges which test their creativity, technical (and googling) skills, and problem-solving ability. Challenges usually cover a number of categories, and when solved, each yields a string (called a flag) which is submitted to an online scoring service. CTFs are a great way to learn a wide array of computer security skills in a safe, legal environment, and are hosted and played by many security groups around the world for fun and practice. For this problem, the flag is: picoCTF{FR3JU3NCY_4774CK5_4R3_C001_7AA384BC}


* FINALMENTE CORREGIMOS LA PALABRA FRECUENCIA EN LA BANDERA *


Flag: picoCTF{FR3QU3NCY_4774CK5_4R3_C001_7AA384BC}
```

## Notas adicionales


## Referencias
- https://www.guballa.de/substitution-solver
