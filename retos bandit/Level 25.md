## Objetivo
Logging in to bandit26 from bandit25 should be fairly easy… The shell for user bandit26 is not **/bin/bash**, but something else. Find out what it is, how it works and how to break out of it.

## Datos de acceso al nivel
**bandit.labs.overthewire.org**
bandit25
p7TaowMYrmu23Ol8hiZh9UvD0O9hpx8d

## Solución
```
bandit25@bandit:~$ cat /etc/passwd | grep bandit26
bandit26:x:11026:11026:bandit level 26:/home/bandit26:/usr/bin/showtext
bandit25@bandit:~$ ls -la /usr/bin/showtext
-rwxr-xr-x 1 root root 58 Oct  5 06:19 /usr/bin/showtext
bandit25@bandit:~$ cat /usr/bin/showtext
#!/bin/sh

export TERM=linux

exec more ~/text.txt
exit 0
bandit25@bandit:~$ ls
bandit26.sshkey
bandit25@bandit:~$ ssh -i bandit26.sshkey bandit26@localhost bandit25@bandit:~$ ssh -i bandit26.sshkey bandit26@localhbandit25@bandit:~$ ssh -i bandit26.sshkey bandit26@localhosbandit25@bandit:~$ ssh -i bandit26.sshkey bandit26@locabandit25@bandit:~$ ssh -i bandit2bandit25@bandit:~$ ssh -i bandit26.sshkey bandit26@lobandit25@bandit:~$ ssh -i banditbandit25@bandit:~$ ssh -i bandit26.sshkey bandit26bandit25@bandit:~$ ssh bandit25@bandit:~$ ssh -i bandit26.sshkey bandit26bandit25@bandit:~$ ssh -i bandit26.sshkey bbandit25@bandit:~$ ssh -i bandbandit25@bandit:~$ ssh -i bandit26.sshkey bandit25@bandit:~$ ssh -i bandit26.sshkey bandit26@localhost -p 2220bandit25@bandit:~$ ssh -i bandit26.sshkeybandit25@bandit:~$ ssh -i bandit26.sshkeybandit25@bandit:~$ ssh -i bandit26.sshkbandit25@banditbandit25@bandbandit25@babandit25@bandit25@bandit:~$ ssh -i bandit2bandit25@bandit:~$ ssh -i bandit2bandit25bandit25@bandit:~$ ssh -i bandibandit25@bandit:~$ ssh -i bandibandit25@bandit:~$ ssh -i bandibandit25@bandit:~$ ssh -i babandit25@bandit:~$ ssh -i bandbandit25@bandit:~$ ssh -i bandbandit25@bandit:~$ ssh -i bandbandit25@bandit:~$ ssh -i bandbandit25@bandit:~$ ssh -i bandbandit25@bandit:~$ ssh -i bandbandbandit25@bandit:~$ ssh -i bandit26.sshkey bandit26@localhost -p 2220
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit25/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit25/.ssh/known_hosts).                         _                     _ _ _
                        | |__   __ _ _ __   __| (_) |_
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_
                        |_.__/ \__,_|_| |_|\__,_|_|\__|


                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames

!!! You are trying to log into this SSH server with a password on port 2220 from localhost.
!!! Connecting from localhost is blocked to conserve resources.
!!! Please log out and log in again.


      ,----..            ,----,          .---.
     /   /   \         ,/   .`|         /. ./|
    /   .     :      ,`   .'  :     .--'.  ' ;
   .   /   ;.  \   ;    ;     /    /__./ \ : |
  .   ;   /  ` ; .'___,/    ,' .--'.  '   \' .
  ;   |  ; \ ; | |    :     | /___/ \ |    ' '
  |   :  | ; | ' ;    |.';  ; ;   \  \;      :
  .   |  ' ' ' : `----'  |  |  \   ;  `      |
  '   ;  \; /  |     '   :  ;   .   \    .\  ;
   \   \  ',  /      |   |  '    \   \   ' \ |
    ;   :    /       '   :  |     :   '  |--"
     \   \ .'        ;   |.'       \   \ ;
  www. `---` ver     '---' he       '---" ire.org


Welcome to OverTheWire!

If you find any problems, please report them to the #wargames channel on
discord or IRC.

--[ Playing the games ]--

  This machine might hold several wargames.
  If you are playing "somegame", then:

    * USERNAMES are somegame0, somegame1, ...
    * Most LEVELS are stored in /somegame/.
    * PASSWORDS for each level are stored in /etc/somegame_pass/.

  Write-access to homedirectories is disabled. It is advised to create a
  working directory with a hard-to-guess name in /tmp/.  You can use the
  command "mktemp -d" in order to generate a random and hard to guess
  directory in /tmp/.  Read-access to both /tmp/ is disabled and to /proc
  restricted so that users cannot snoop on eachother. Files and directories
  with easily guessable or short names will be periodically deleted! The /tmp
  directory is regularly wiped.
  Please play nice:

    * don't leave orphan processes running
    * don't leave exploit-files laying around
    * don't annoy other players
    * don't post passwords or spoilers
    * again, DONT POST SPOILERS!
      This includes writeups of your solution on your blog or website!

--[ Tips ]--

  This machine has a 64bit processor and many security-features enabled
  by default, although ASLR has been switched off.  The following
  compiler flags might be interesting:

    -m32                    compile for 32bit
    -fno-stack-protector    disable ProPolice
    -Wl,-z,norelro          disable relro

  In addition, the execstack tool can be used to flag the stack as
  executable on ELF binaries.

  Finally, network-access is limited for most levels by a local
  firewall.

--[ Tools ]--

 For your convenience we have installed a few useful tools which you can find
 in the following locations:
    * gef (https://github.com/hugsy/gef) in /opt/gef/
    * pwndbg (https://github.com/pwndbg/pwndbg) in /opt/pwndbg/
    * peda (https://github.com/longld/peda.git) in /opt/peda/
    * gdbinit (https://github.com/gdbinit/Gdbinit) in /opt/gdbinit/
    * pwntools (https://github.com/Gallopsled/pwntools)
    * radare2 (http://www.radare.org/)

--[ More information ]--

  For more information regarding individual wargames, visit
  http://www.overthewire.org/wargames/

  For support, questions or comments, contact us on discord or IRC.

  Enjoy your stay!

  _                     _ _

  _                     _ _ _   ___   __
 | |                   | (_) | |__ \ / /
 | |__   __ _ _ __   __| |_| |_   ) / /_
 '_ \ / _` | '_ \ / _` | | __| / / '_ \
  _                     _ _ _   ___   __
 | |                   | (_) | |__ \ / /
 | |__   __ _ _ __   __| |_| |_   ) / /_
'_ \ / _` | '_ \ / _` | | __| / / '_ \
 | |_) | (_| | | | | (_| | | |_ / /| (_) |
 |_.__/ \__,_|_| |_|\__,_|_|\__|____\___/
~                                                                                                          ~                                                                                                          ~                                                                                                          ~                                                                                                          ~                                                                                                          ~                                                                                                          ~                                                                                                          ~                                                                                                          ~                                                                                                          ~                                                                                                          ~                                                                                                          ~                                                                                                          ~
~                                                                                                         :shell
[No write since last change] |_ / /| (_) |
bandit26@bandit:~$ whoami
bandit26                                                                                 ~
bandit26@bandit:~$ cat /etc/bandit_pass/bandit26                       ~
c7GvcKlw9mC7aUQaPx7nwFstuAIBw1o1
```

## Notas adicionales
- Al hacer mas chica la ventana forzamos a que la salida sea mostrada con el comando more
- En el comando more podemos teclear la letra v para entrar en el editor de vim

## Referencias
- https://medium.com/@coturnix97/overthewires-bandit-25-26-shell-355d78fd2f4d
