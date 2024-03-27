## Objetivo
Can you get the real meaning from this file.Download the file [here](https://artifacts.picoctf.net/c_titan/108/enc_flag).

## Pistas

## Solución
1. Ir a terminal de Linux y hacer lo siguiente:
```
xarom-picoctf@webshell:~/picoCTF2024$ mkdir interencdec
xarom-picoctf@webshell:~/picoCTF2024$ cd interencdec/
xarom-picoctf@webshell:~/picoCTF2024/interencdec$ wget https://artifacts.picoctf.net/c_titan/108/enc_flag
--2024-03-16 22:25:06--  https://artifacts.picoctf.net/c_titan/108/enc_flag
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.5.18, 3.160.5.93, 3.160.5.71, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.5.18|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 73 [application/octet-stream]
Saving to: 'enc_flag'

enc_flag                                                   100%[=======================================================================================================================================>]      73  --.-KB/s    in 0s      

2024-03-16 22:25:06 (3.82 MB/s) - 'enc_flag' saved [73/73]

xarom-picoctf@webshell:~/picoCTF2024/interencdec$ cat enc_flag 
YidkM0JxZGtwQlRYdHFhR3g2YUhsZmF6TnFlVGwzWVROclgyZzBOMm8yYXpZNWZRPT0nCg==
xarom-picoctf@webshell:~/picoCTF2024/interencdec$ cat enc_flag | base64 -d
b'd3BqdkpBTXtqaGx6aHlfazNqeTl3YTNrX2g0N2o2azY5fQ=='
xarom-picoctf@webshell:~/picoCTF2024/interencdec$ echo 'd3BqdkpBTXtqaGx6aHlfazNqeTl3YTNrX2g0N2o2azY5fQ==' | base64 -d
wpjvJAM{jhlzhy_k3jy9wa3k_h47j6k69}
xarom-picoctf@webshell:~/picoCTF2024/interencdec$ 
```
2. Ir a https://cryptii.com/pipes/caesar-cipher y dar click en decode.
3. Copiar wpjvMDP{jhlzhy_k3jy9wa3k_h47j6k69} en la caja de texto de Ciphertext.
4. La bandera es :
picoCTF{caesar_d3cr9pt3d_a47c6d69}
## Notas adicionales

## Referencias
