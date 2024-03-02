## Objetivo
Fix the syntax error in the Python script to print the flag.[Download Python script](https://artifacts.picoctf.net/c/5/fixme2.py)

## Pistas
- Are equality and assignment the same symbol?
- To view the file in the webshell, do: `$ nano fixme2.py`
- To exit `nano`, press Ctrl and x and follow the on-screen prompts.
- The `str_xor` function does not need to be reverse engineered for this challenge.

## Solución
```
elyahir-picoctf@webshell:~/fixme2$ ls
fixme2.py
elyahir-picoctf@webshell:~/fixme2$ python3 fixme2.py 
  File "/home/elyahir-picoctf/fixme2/fixme2.py", line 22
    if flag = "":
       ^^^^^^^^^
SyntaxError: invalid syntax. Maybe you meant '==' or ':=' instead of '='?
elyahir-picoctf@webshell:~/fixme2$ nano fixme2.py 
elyahir-picoctf@webshell:~/fixme2$ python3 fixme2.py 
That is correct! Here's your flag: picoCTF{3qu4l1ty_n0t_4551gnm3nt_4863e11b}
```

## Notas adicionales


## Referencias

