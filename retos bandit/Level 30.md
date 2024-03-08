## Objetivo
There is a git repository at `ssh://bandit30-git@localhost/home/bandit30-git/repo` via the port `2220`. The password for the user `bandit30-git` is the same as for the user `bandit30`.

Clone the repository and find the password for the next level.

## Datos de acceso al nivel
**bandit.labs.overthewire.org**
bandit30
xbhV3HpNGlTIdnjUrdAlPzc2L6y9EOnS

## Solución
```
bandit30@bandit:~$ mktemp -d
/tmp/tmp.eUTRKR1JMI
bandit30@bandit:~$ cd /tmp/tmp.eUTRKR1JMI
bandit30@bandit:/tmp/tmp.eUTRKR1JMI$ git clone ssh://bandit30-git@localhost:2220/home/bandit30-git/repo
Cloning into 'repo'...
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit30/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit30/.ssh/known_hosts).
                         _                     _ _ _
                        | |__   __ _ _ __   __| (_) |_
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_
                        |_.__/ \__,_|_| |_|\__,_|_|\__|


                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames

bandit30-git@localhost's password:
remote: Enumerating objects: 4, done.
remote: Counting objects: 100% (4/4), done.
remote: Total 4 (delta 0), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (4/4), done.
bandit30@bandit:/tmp/tmp.eUTRKR1JMI$ ls
repo
bandit30@bandit:/tmp/tmp.eUTRKR1JMI$ cd repo/
bandit30@bandit:/tmp/tmp.eUTRKR1JMI/repo$ ls
README.md
bandit30@bandit:/tmp/tmp.eUTRKR1JMI/repo$ cat README.md
just an epmty file... muahaha
bandit30@bandit:/tmp/tmp.eUTRKR1JMI/repo$ git log
commit d39631d73f786269b895ae9a7b14760cbf40a99f (HEAD -> master, origin/master, origin/HEAD)
Author: Ben Dover <noone@overthewire.org>
Date:   Thu Oct 5 06:19:45 2023 +0000

    initial commit of README.md
bandit30@bandit:/tmp/tmp.eUTRKR1JMI/repo$ git branch -a
* master
  remotes/origin/HEAD -> origin/master
  remotes/origin/master
bandit30@bandit:/tmp/tmp.eUTRKR1JMI/repo$ git checkout master
Already on 'master'
Your branch is up to date with 'origin/master'.
bandit30@bandit:/tmp/tmp.eUTRKR1JMI/repo$ ls
README.md
bandit30@bandit:/tmp/tmp.eUTRKR1JMI/repo$ cat README.md
just an epmty file... muahaha
bandit30@bandit:/tmp/tmp.eUTRKR1JMI/repo$ git log
commit d39631d73f786269b895ae9a7b14760cbf40a99f (HEAD -> master, origin/master, origin/HEAD)
Author: Ben Dover <noone@overthewire.org>
Date:   Thu Oct 5 06:19:45 2023 +0000

    initial commit of README.md
bandit30@bandit:/tmp/tmp.eUTRKR1JMI/repo$ git checkout origin/master
Note: switching to 'origin/master'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

Or undo this operation with:

  git switch -

Turn off this advice by setting config variable advice.detachedHead to false

HEAD is now at d39631d initial commit of README.md
bandit30@bandit:/tmp/tmp.eUTRKR1JMI/repo$ git branch
* (HEAD detached at origin/master)
  master
bandit30@bandit:/tmp/tmp.eUTRKR1JMI/repo$ ls
README.md
bandit30@bandit:/tmp/tmp.eUTRKR1JMI/repo$ cat README.md
just an epmty file... muahaha
bandit30@bandit:/tmp/tmp.eUTRKR1JMI/repo$ git tag
secret
bandit30@bandit:/tmp/tmp.eUTRKR1JMI/repo$ git show secret
OoffzGDlzhAlerFJ2cAiz1D41JW1Mhmt
bandit30@bandit:/tmp/tmp.eUTRKR1JMI/repo$ exit
```

## Notas adicionales
- El comando git tag nos permite ver los tags de commits especificos

## Referencias
- https://dzone.com/articles/top-20-git-commands-with-examples
