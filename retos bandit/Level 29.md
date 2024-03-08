## Objetivo
There is a git repository at `ssh://bandit29-git@localhost/home/bandit29-git/repo` via the port `2220`. The password for the user `bandit29-git` is the same as for the user `bandit29`.

Clone the repository and find the password for the next level.

## Datos de acceso al nivel
**bandit.labs.overthewire.org**
bandit29
tQKvmcwNYcFS6vmPHIUSI3ShmsrQZK8S

## Solución
```
bandit29@bandit:~$ mktemp -d
/tmp/tmp.5vGnn5bm7e
bandit29@bandit:~$ cd /tmp/tmp.5vGnn5bm7e
bandit29@bandit:/tmp/tmp.5vGnn5bm7e$ git clone ssh://bandit29-git@localhost:2220/home/bandit29-git/repo
Cloning into 'repo'...
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit29/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit29/.ssh/known_hosts).
                         _                     _ _ _
                        | |__   __ _ _ __   __| (_) |_
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_
                        |_.__/ \__,_|_| |_|\__,_|_|\__|


                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames

bandit29-git@localhost's password:
remote: Enumerating objects: 16, done.
remote: Counting objects: 100% (16/16), done.
remote: Compressing objects: 100% (11/11), done.
remote: Total 16 (delta 2), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (16/16), done.
Resolving deltas: 100% (2/2), done.
bandit29@bandit:/tmp/tmp.5vGnn5bm7e$ ls
repo
bandit29@bandit:/tmp/tmp.5vGnn5bm7e$ cd repo/
bandit29@bandit:/tmp/tmp.5vGnn5bm7e/repo$ ls
README.md
bandit29@bandit:/tmp/tmp.5vGnn5bm7e/repo$ cat README.md
# Bandit Notes
Some notes for bandit30 of bandit.

## credentials

- username: bandit30
- password: <no passwords in production!>

bandit29@bandit:/tmp/tmp.5vGnn5bm7e/repo$ git branch -a
* master
  remotes/origin/HEAD -> origin/master
  remotes/origin/dev
  remotes/origin/master
  remotes/origin/sploits-dev
bandit29@bandit:/tmp/tmp.5vGnn5bm7e/repo$ git checkout dev
Branch 'dev' set up to track remote branch 'dev' from 'origin'.
Switched to a new branch 'dev'
bandit29@bandit:/tmp/tmp.5vGnn5bm7e/repo$ ls
code  README.md
bandit29@bandit:/tmp/tmp.5vGnn5bm7e/repo$ cat README.md
# Bandit Notes
Some notes for bandit30 of bandit.

## credentials

- username: bandit30
- password: xbhV3HpNGlTIdnjUrdAlPzc2L6y9EOnS

bandit29@bandit:/tmp/tmp.5vGnn5bm7e/repo$ exit
```

## Notas adicionales
- El comando git branch nos permite crear nuevas ramas
- El parametro -a en el comando git branch nos muestra todas las ramas que hay
- El comando git checkout nos permite cambiar de rama

## Referencias

