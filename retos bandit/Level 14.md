## Objetivo
The password for the next level can be retrieved by submitting the password of the current level to **port 30000 on localhost**.

## Datos de acceso al nivel
**bandit.labs.overthewire.org**
bandit14
fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq
## Solución
```
bandit14@bandit:~$ echo "fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq" | nc localhost 30000
Correct!
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt

bandit14@bandit:~$ exit
```

## Notas adicionales
- El comando *nc* permite acceder a puertos TCP o UDP de la propia máquina o de otras máquinas remotas.
- Con el echo mandamos la salida estandar al puerto 30000 por medio del comando nc

## Referencias
- https://www.ochobitshacenunbyte.com/2021/11/04/uso-del-comando-ncat-nc-en-linux-con-ejemplos/