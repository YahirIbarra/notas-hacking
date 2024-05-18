## Objetivo
A musician left us a [message](https://jupiter.challenges.picoctf.org/static/d5570d48262dbba2a31f2a940409ad9d/message.txt). What's it mean?

## Pistas


## Solución
```
┌──(kali㉿kali)-[~/Documents/Retos/tercer-parcial/mr-worldwide]
└─$ cat message.txt           
picoCTF{(35.028309, 135.753082)(46.469391, 30.740883)(39.758949, -84.191605)(41.015137, 28.979530)(24.466667, 54.366669)(3.140853, 101.693207)_(9.005401, 38.763611)(-3.989038, -79.203560)(52.377956, 4.897070)(41.085651, -73.858467)(57.790001, -152.407227)(31.205753, 29.924526)} 

* SEPARAR LOS DATOS DE MANERA MAS VISIBLE *

picoCTF{
35.028309, 135.753082
46.469391, 30.740883
39.758949, -84.191605
41.015137, 28.979530
24.466667, 54.366669
3.140853, 101.693207
_
9.005401, 38.763611
-3.989038, -79.203560
52.377956, 4.897070
41.085651, -73.858467
57.790001, -152.407227
31.205753, 29.924526
}

* BUSCAR UBICACIONES EN GOOGLE MAPS *

picoCTF{
35.028309, 135.753082    Kyoto, Japan
46.469391, 30.740883     Odesa, Ukrain
39.758949, -84.191605    Dayton, Ohio
41.015137, 28.979530     Istanbul, Turkey
24.466667, 54.366669     Abu Dhabi, United Arab Emirates
3.140853, 101.693207     Kuala Lumpur, Malaysia 
_
9.005401, 38.763611      Addis Ababa, Ethiopia
-3.989038, -79.203560    Loja, Ecquador
52.377956, 4.897070      Amsterdam, Netherlands
41.085651, -73.858467    Sleepy Hollow, New York
57.790001, -152.407227   Kodiak, Alaska
31.205753, 29.924526     Alexandria Governorate, Egypt
} 


Flag: picoCTF{KODIAK_ALASKA}
```

## Notas adicionales


## Referencias

