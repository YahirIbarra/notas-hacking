## Objetivo
To get truly 1337, you must understand different data encodings, such as hexadecimal or binary. Can you get the flag from this program to prove you are on the way to becoming 1337? Connect with `nc jupiter.challenges.picoctf.org 15130`.

## Pistas
- I hear python can convert things.
- It might help to have multiple windows open.

## Solución
```
elyahir-picoctf@webshell:~$ nc jupiter.challenges.picoctf.org 15130
Let us see how data is stored
container
Please give the 01100011 01101111 01101110 01110100 01100001 01101001 01101110 01100101 01110010 as a word.
...
you have 45 seconds.....

Input:
container
Please give me the  155 141 160 as a word.
Input:
map
Please give me the 74657374 as a word.
Input:
test
You've beaten the challenge
Flag: picoCTF{learning_about_converting_values_02167de8}
```

## Notas adicionales
- CyberChef es una herramienta que permite detectar el tipo de base en la que se encuentra cualquier texto, ademas de traducirlo

## Referencias
- https://www.rapidtables.com/convert/number/binary-to-ascii.html
- https://onlinetools.com/ascii/convert-octal-to-ascii
- https://gchq.github.io/CyberChef/#recipe=From_Hex('None')&input=NzQ2NTczNzQ
