## Objetivo
There is a setuid binary in the homedirectory that does the following: it makes a connection to localhost on the port you specify as a commandline argument. It then reads a line of text from the connection and compares it to the password in the previous level (bandit20). If the password is correct, it will transmit the password for the next level (bandit21).

**NOTE:** Try connecting to your own network daemon to see if it works as you think

## Datos de acceso al nivel
**bandit.labs.overthewire.org**
bandit20
VxCazJaVykI6W36BkBU0mJTCM8rR95XT
## Solución
```
bandit20@bandit:~$ nc -lnvp 1994 <<< VxCazJaVykI6W36BkBU0mJTCM8rR95XT &
[1] 145908
bandit20@bandit:~$ Listening on 0.0.0.0 1994
^C
bandit20@bandit:~$ nc -lnvp 1994 <<< VxCazJaVykI6W36BkBU0mJTCM8rR95XT &
[2] 146979
bandit20@bandit:~$ Listening on 0.0.0.0 1994
./sudoconnect 1994
-bash: ./sudoconnect: No such file or directory
bandit20@bandit:~$ ./sudoconnect 1994
-bash: ./sudoconnect: No such file or directory
bandit20@bandit:~$ ./suconnect jobs
getaddrinfo: Servname not supported for ai_socktype
bandit20@bandit:~$ jobs
[1]-  Running                 nc -lnvp 1994 <<< VxCazJaVykI6W36BkBU0mJTCM8rR95XT &
[2]+  Running                 nc -lnvp 1994 <<< VxCazJaVykI6W36BkBU0mJTCM8rR95XT &
bandit20@bandit:~$ ./suconnect 1994
Connection received on 127.0.0.1 51868
Read: VxCazJaVykI6W36BkBU0mJTCM8rR95XT
Password matches, sending next password
NvEJF7oVjkddltPSrdKEFOllh9V1IBcq
[2]+  Done                    nc -lnvp 1994 <<< VxCazJaVykI6W36BkBU0mJTCM8rR95XT
bandit20@bandit:~$ exit
```

## Notas adicionales
- Para abrir un puerto es necesario el parametro -lnvp en el comando nc

## Referencias

