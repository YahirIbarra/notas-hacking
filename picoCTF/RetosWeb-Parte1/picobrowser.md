## Objetivo
This website can be rendered only by **picobrowser**, go and catch the flag! `https://jupiter.challenges.picoctf.org/problem/50522/` ([link](https://jupiter.challenges.picoctf.org/problem/50522/)) or http://jupiter.challenges.picoctf.org:50522

## Pistas
- You don't need to download a new web browser

## Solución
```
elyahir-picoctf@webshell:~$ curl https://jupiter.challenges.picoctf.org/problem/50522/flag -H "User-Agent:picobrowser" | grep picoCTF
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100  2115  100  2115    0     0   5136      0 --:--:-- --:--:-- --:--:--  5145
            <p style="text-align:center; font-size:30px;"><b>Flag</b>: <code>picoCTF{p1c0_s3cr3t_ag3nt_51414fa7}</code></p>
elyahir-picoctf@webshell:~$ ^C
elyahir-picoctf@webshell:~$ curl https://jupiter.challenges.picoctf.org/problem/50522/flag -A picobrowser | grep picoCTF
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100  2115  100  2115    0     0   5049      0 --:--:-- --:--:-- --:--:--  5059
            <p style="text-align:center; font-size:30px;"><b>Flag</b>: <code>picoCTF{p1c0_s3cr3t_ag3nt_51414fa7}</code></p>
```

## Notas adicionales
- El comando curl con el parametro -H puede enviar un user agent diferente
- Tambien se puede utilizar el parametro -A para especificar el user agent

## Referencias

