## Objetivo
Know of little and big endian?

Additional details will be available after launching your challenge instance.

## Pistas
- You might want to check the ASCII table to first find the hexadecimal representation of characters before finding the endianness.
- Read more about how endianness [here](https://levelup.gitconnected.com/little-endian-and-big-endian-74ab6441b2a7)

## Solución
```
elyahir-picoctf@webshell:~/picoCTF2024/endianness$ nc titan.picoctf.net 63991
Welcome to the Endian CTF!
You need to find both the little endian and big endian representations of a word.
If you get both correct, you will receive the flag.
Word: eqqam
Enter the Little Endian representation: 6D61717165
Correct Little Endian representation!
Enter the Big Endian representation: 657171616D
Correct Big Endian representation!
Congratulations! You found both endian representations correctly!
Your Flag is: picoCTF{3ndi4n_sw4p_su33ess_28329f0a}

^C
elyahir-picoctf@webshell:~/picoCTF2024/endianness$ 
```

## Notas adicionales


## Referencias
- https://gchq.github.io/CyberChef/#recipe=To_Hex('Space',0)&input=ZXFxYW0
- https://www.save-editor.com/tools/wse_hex.html
