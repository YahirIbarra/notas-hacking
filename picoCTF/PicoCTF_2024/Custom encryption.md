## Objetivo
Can you get sense of this code file and write the function that will decode the given encrypted file content.Find the encrypted file here [flag_info](https://artifacts.picoctf.net/c_titan/92/enc_flag) and [code file](https://artifacts.picoctf.net/c_titan/92/custom_encryption.py) might be good to analyze and get the flag.

## Pistas

## Solución
1. Ir a terminal de Linux y hacer lo siguiente:
```
kali@kali:~/Documents/picoCTF/picoCTF2024$ mkdir custom_encryption

kali@kali:~/Documents/picoCTF/picoCTF2024$ cd custom_encryption

kali@kali:~/Documents/picoCTF/picoCTF2024/custom_encryption$ wget https://artifacts.picoctf.net/c_titan/92/enc_flag
--2024-03-19 21:12:51--  https://artifacts.picoctf.net/c_titan/92/enc_flag
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 2600:9000:26c9:5800:16:5ec5:2840:93a1, 2600:9000:26c9:f600:16:5ec5:2840:93a1, 2600:9000:26c9:b800:16:5ec5:2840:93a1, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|2600:9000:26c9:5800:16:5ec5:2840:93a1|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 270 [application/octet-stream]
Saving to: ‘enc_flag’

enc_flag                                                   100%[=======================================================================================================================================>]     270  --.-KB/s    in 0s      

2024-03-19 21:12:52 (303 MB/s) - ‘enc_flag’ saved [270/270]


kali@kali:~/Documents/picoCTF/picoCTF2024/custom_encryption$ wget https://artifacts.picoctf.net/c_titan/92/custom_encryption.py
--2024-03-19 21:16:24--  https://artifacts.picoctf.net/c_titan/92/custom_encryption.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 2600:9000:26c9:e00:16:5ec5:2840:93a1, 2600:9000:26c9:3200:16:5ec5:2840:93a1, 2600:9000:26c9:b400:16:5ec5:2840:93a1, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|2600:9000:26c9:e00:16:5ec5:2840:93a1|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1411 (1.4K) [application/octet-stream]
Saving to: ‘custom_encryption.py’

custom_encryption.py                                       100%[=======================================================================================================================================>]   1.38K  --.-KB/s    in 0s      

2024-03-19 21:16:25 (23.4 MB/s) - ‘custom_encryption.py’ saved [1411/1411]




```
2. La bandera es :
picoCTF{ME74D47A_HIDD3N_3b9209a2}
## Notas adicionales

## Referencias
