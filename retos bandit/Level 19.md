## Objetivo
To gain access to the next level, you should use the setuid binary in the homedirectory. Execute it without arguments to find out how to use it. The password for this level can be found in the usual place (/etc/bandit_pass), after you have used the setuid binary.

## Datos de acceso al nivel
**bandit.labs.overthewire.org**
bandit19
awhqfNnAbc1naukrpqDYcF95h7HoMTrC
## Solución
```
bandit19@bandit:~$ ls -la
total 36
drwxr-xr-x  2 root     root      4096 Oct  5 06:19 .
drwxr-xr-x 70 root     root      4096 Oct  5 06:20 ..
-rwsr-x---  1 bandit20 bandit19 14876 Oct  5 06:19 bandit20-do
-rw-r--r--  1 root     root       220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root     root      3771 Jan  6  2022 .bashrc
-rw-r--r--  1 root     root       807 Jan  6  2022 .profile
bandit19@bandit:~$ file bandit20-do
bandit20-do: setuid ELF 32-bit LSB executable, Intel 80386, version 1 (SYSV), dynamically linked, interpreter /lib/ld-linux.so.2, BuildID[sha1]=037b97b430734c79085a8720c90070e346ca378e, for GNU/Linux 3.2.0, not stripped
bandit19@bandit:~$ uid
Command 'uid' not found, did you mean:
  command 'gid' from deb id-utils (4.6.28-20200521ss15dab)
  command 'uil' from deb uil (2.3.8-3)
  command 'umd' from deb node-umd (3.0.3+ds+~3.0.1-1)
  command 'id' from deb coreutils (8.32-4.1ubuntu1)
  command 'aid' from deb id-utils (4.6.28-20200521ss15dab)
  command 'jid' from deb jid (0.7.6-1)
  command 'uif' from deb uif (1.1.9-5)
  command 'uuid' from deb uuid (1.6.2-1.5build9)
  command 'lid' from deb id-utils (4.6.28-20200521ss15dab)
  command 'uic' from deb qtchooser (66-2build1)
  command 'eid' from deb id-utils (4.6.28-20200521ss15dab)
  command 'ui' from deb userinfo (2.5-5)
  command 'fid' from deb id-utils (4.6.28-20200521ss15dab)
Try: apt install <deb name>
bandit19@bandit:~$ id
uid=11019(bandit19) gid=11019(bandit19) groups=11019(bandit19)
bandit19@bandit:~$ id bandit20
uid=11020(bandit20) gid=11020(bandit20) groups=11020(bandit20)
bandit19@bandit:~$ ./bandit20-do
Run a command as another user.
  Example: ./bandit20-do id
bandit19@bandit:~$ ./bandit20-do id 11020
uid=11020(bandit20) gid=11020(bandit20) groups=11020(bandit20)
bandit19@bandit:~$ ./bandit20-do cat /etc/bandit_pass/bandit20
VxCazJaVykI6W36BkBU0mJTCM8rR95XT
bandit19@bandit:~$ cat /etc/bandit_pass/bandit20
cat: /etc/bandit_pass/bandit20: Permission denied
bandit19@bandit:~$ exit
```

## Notas adicionales
- El comando *setuid* nos permite ejecutar comandos a nombre de otros usuarios (en este caso el archivo bandit20-do nos permite ejecutar comandos a nombre del usuario bandit20)

## Referencias

