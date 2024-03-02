## Objetivo
Run the Python script `code.py` in the same directory as `codebook.txt`.

- [Download code.py](https://artifacts.picoctf.net/c/1/code.py)
- [Download codebook.txt](https://artifacts.picoctf.net/c/1/codebook.txt)

## Pistas
- On the webshell, use `ls` to see if both files are in the directory you are in
- The `str_xor` function does not need to be reverse engineered for this challenge.

## Solución
```
elyahir-picoctf@webshell:~/codebook$ wget https://artifacts.picoctf.net/c/1/code.py
--2024-03-02 18:36:01--  https://artifacts.picoctf.net/c/1/code.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.128, 3.160.22.43, 3.160.22.92, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.128|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1278 (1.2K) [application/octet-stream]
Saving to: 'code.py'

code.py                                                   100%[==================================================================================================================================>]   1.25K  --.-KB/s    in 0s      

2024-03-02 18:36:01 (337 MB/s) - 'code.py' saved [1278/1278]

elyahir-picoctf@webshell:~/codebook$ wget https://artifacts.picoctf.net/c/1/codebook.txt
--2024-03-02 18:36:17--  https://artifacts.picoctf.net/c/1/codebook.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.43, 3.160.22.92, 3.160.22.16, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.43|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 27 [application/octet-stream]
Saving to: 'codebook.txt'

codebook.txt                                              100%[==================================================================================================================================>]      27  --.-KB/s    in 0s      

2024-03-02 18:36:18 (16.3 MB/s) - 'codebook.txt' saved [27/27]

elyahir-picoctf@webshell:~/codebook$ ls
code.py  codebook.txt
elyahir-picoctf@webshell:~/codebook$ python3
Python 3.10.6 (main, Aug 10 2022, 11:40:04) [GCC 11.3.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> quit
Use quit() or Ctrl-D (i.e. EOF) to exit
>>> quit()
elyahir-picoctf@webshell:~/codebook$ python3 code.py 
picoCTF{c0d3b00k_455157_d9aa2df2}
```

## Notas adicionales


## Referencias

