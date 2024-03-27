## Objetivo
How well can you perfom basic binary operations?Start searching for the flag here `nc titan.picoctf.net 56491`

## Pistas
How well can you perfom basic binary operations?Start searching for the flag here `nc titan.picoctf.net 56491`

## Solución
```
elyahir-picoctf@webshell:~/picoCTF2024$ nc titan.picoctf.net 56491

Welcome to the Binary Challenge!"
Your task is to perform the unique operations in the given order and find the final result in hexadecimal that yields the flag.

Binary Number 1: 00111010
Binary Number 2: 11110100


Question 1/6:
Operation 1: '>>'
Perform a right shift of Binary Number 2 by 1 bits .
Enter the binary result: 1111010
Correct!

Question 2/6:
Operation 2: '|'
Perform the operation on Binary Number 1&2.
Enter the binary result: 11111110
Correct!

Question 3/6:
Operation 3: '&'
Perform the operation on Binary Number 1&2.
Enter the binary result: 110000
Correct!

Question 4/6:
Operation 4: '<<'
Perform a left shift of Binary Number 1 by 1 bits.
Enter the binary result: 1110100
Correct!

Question 5/6:
Operation 5: '+'
Perform the operation on Binary Number 1&2.
Enter the binary result: 100101110
Correct!

Question 6/6:
Operation 6: '*'
Perform the operation on Binary Number 1&2.
Enter the binary result: 11011101001000
Correct!

Enter the results of the last operation in hexadecimal: 0x3748

Correct answer!
The flag is: picoCTF{b1tw^3se_0p3eR@tI0n_su33essFuL_6862762d}
^C
```

## Notas adicionales


## Referencias
- https://www.onlinegdb.com
- https://gchq.github.io/CyberChef/
- https://www.rapidtables.com/convert/number/
