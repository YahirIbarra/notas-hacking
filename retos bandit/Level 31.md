## Objetivo
There is a git repository at `ssh://bandit31-git@localhost/home/bandit31-git/repo` via the port `2220`. The password for the user `bandit31-git` is the same as for the user `bandit31`.

Clone the repository and find the password for the next level.

## Datos de acceso al nivel
**bandit.labs.overthewire.org**
bandit31
OoffzGDlzhAlerFJ2cAiz1D41JW1Mhmt

## Solución
```
bandit31@bandit:~$ mktemp -d
/tmp/tmp.4p2KhAOFpv
bandit31@bandit:~$ cd /tmp/tmp.4p2KhAOFpv
bandit31@bandit:/tmp/tmp.4p2KhAOFpv$ git clone ssh://bandit31-git@localhost:2220/home/bandit31-git/repo
Cloning into 'repo'...
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit31/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit31/.ssh/known_hosts).
                         _                     _ _ _
                        | |__   __ _ _ __   __| (_) |_
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_
                        |_.__/ \__,_|_| |_|\__,_|_|\__|


                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames

bandit31-git@localhost's password:
remote: Enumerating objects: 4, done.
remote: Counting objects: 100% (4/4), done.
remote: Compressing objects: 100% (3/3), done.
remote: Total 4 (delta 0), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (4/4), done.
bandit31@bandit:/tmp/tmp.4p2KhAOFpv$ ls
repo
bandit31@bandit:/tmp/tmp.4p2KhAOFpv$ cd repo/
bandit31@bandit:/tmp/tmp.4p2KhAOFpv/repo$ ls
README.md
bandit31@bandit:/tmp/tmp.4p2KhAOFpv/repo$ cat README.md
This time your task is to push a file to the remote repository.

Details:
    File name: key.txt
    Content: 'May I come in?'
    Branch: master

bandit31@bandit:/tmp/tmp.4p2KhAOFpv/repo$ echo 'May I come in?' > key.txt
bandit31@bandit:/tmp/tmp.4p2KhAOFpv/repo$ ls -la
total 24
drwxrwxr-x 3 bandit31 bandit31 4096 Mar  8 03:42 .
drwx------ 3 bandit31 bandit31 4096 Mar  8 03:42 ..
drwxrwxr-x 8 bandit31 bandit31 4096 Mar  8 03:42 .git
-rw-rw-r-- 1 bandit31 bandit31    6 Mar  8 03:42 .gitignore
-rw-rw-r-- 1 bandit31 bandit31   15 Mar  8 03:42 key.txt
-rw-rw-r-- 1 bandit31 bandit31  147 Mar  8 03:42 README.md
bandit31@bandit:/tmp/tmp.4p2KhAOFpv/repo$ cat key.txt
May I come in?
bandit31@bandit:/tmp/tmp.4p2KhAOFpv/repo$ cat .gitignore
*.txt
bandit31@bandit:/tmp/tmp.4p2KhAOFpv/repo$ git add -f key.txt
bandit31@bandit:/tmp/tmp.4p2KhAOFpv/repo$ git commit -a
Unable to create directory /home/bandit31/.local/share/nano/: No such file or directory
It is required for saving/loading search history or cursor positions.

Aborting commit due to empty commit message.
bandit31@bandit:/tmp/tmp.4p2KhAOFpv/repo$ git status
On branch master
Your branch is up to date with 'origin/master'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   key.txt

bandit31@bandit:/tmp/tmp.4p2KhAOFpv/repo$ git commit -m "Subiendo archivo"
[master e4071c9] Subiendo archivo
 1 file changed, 1 insertion(+)
 create mode 100644 key.txt
bandit31@bandit:/tmp/tmp.4p2KhAOFpv/repo$ git staus
git: 'staus' is not a git command. See 'git --help'.

The most similar command is
        status
bandit31@bandit:/tmp/tmp.4p2KhAOFpv/repo$ git status
On branch master
Your branch is ahead of 'origin/master' by 1 commit.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean
bandit31@bandit:/tmp/tmp.4p2KhAOFpv/repo$ git push origin master
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit31/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit31/.ssh/known_hosts).
                         _                     _ _ _
                        | |__   __ _ _ __   __| (_) |_
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_
                        |_.__/ \__,_|_| |_|\__,_|_|\__|


                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames

bandit31-git@localhost's password:
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 2 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 327 bytes | 327.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
remote: ### Attempting to validate files... ####
remote:
remote: .oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.
remote:
remote: Well done! Here is the password for the next level:
remote: rmCBvG56y58BXzv98yZGdO7ATVL5dW8y
remote:
remote: .oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.
remote:
To ssh://localhost:2220/home/bandit31-git/repo
 ! [remote rejected] master -> master (pre-receive hook declined)
error: failed to push some refs to 'ssh://localhost:2220/home/bandit31-git/repo'
bandit31@bandit:/tmp/tmp.4p2KhAOFpv/repo$ exit
```

## Notas adicionales
- El archivo gitignore posee en nombre de archivos que seran ignorados al hacer push
- El parametro -f en git add nos permite forzar el añadido de un archivo que no es permitido en el gitignore

## Referencias
- https://git-scm.com/docs
