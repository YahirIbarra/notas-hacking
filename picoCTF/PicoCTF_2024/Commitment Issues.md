## Objetivo
I accidentally wrote the flag down. Good thing I deleted it!You download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/136/challenge.zip)

## Pistas
- Version control can help you recover files if you change or lose them!
- Read the chapter on Git from the picoPrimer [here](https://primer.picoctf.org/#_git_version_control)
- You can 'checkout' commits to see the files inside them

## Solución
```
elyahir-picoctf@webshell:~/picoCTF2024/drop-in$ ls
message.txt
elyahir-picoctf@webshell:~/picoCTF2024/drop-in$ ls -la
total 4
drwxr-xr-x 3 elyahir-picoctf elyahir-picoctf  37 Mar 12 00:06 .
drwxrwxr-x 3 elyahir-picoctf elyahir-picoctf  42 Mar 15 02:43 ..
drwxr-xr-x 8 elyahir-picoctf elyahir-picoctf 166 Mar 12 00:06 .git
-rw-r--r-- 1 elyahir-picoctf elyahir-picoctf  11 Mar 12 00:06 message.txt
elyahir-picoctf@webshell:~/picoCTF2024/drop-in$ cat message.txt 
TOP SECRET
elyahir-picoctf@webshell:~/picoCTF2024/drop-in$ git show

commit 8dc51806c760dfdbb34b33a2008926d3d8e8ad49 (HEAD -> master)
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:06:17 2024 +0000

    remove sensitive info

diff --git a/message.txt b/message.txt
index bae247d..d552d1e 100644
--- a/message.txt
+++ b/message.txt
@@ -1 +1 @@
-picoCTF{s@n1t1z3_ea83ff2a}
+TOP SECRET
(END)
```

## Notas adicionales


## Referencias

