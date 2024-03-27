## Objetivo
What was I last working on? I remember writing a note to help me remember...You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/160/challenge.zip)

## Pistas
- The `cat` command will let you read a file, but that won't help you here!
- Read the chapter on Git from the picoPrimer [here](https://primer.picoctf.org/#_git_version_control).
- When committing a file with git, a message can (and should) be included.

## Solución
```
elyahir-picoctf@webshell:~/picoCTF2024/time_machine$ ls
challenge.zip  drop-in
elyahir-picoctf@webshell:~/picoCTF2024/time_machine$ cd drop-in/
elyahir-picoctf@webshell:~/picoCTF2024/time_machine/drop-in$ ls
message.txt
elyahir-picoctf@webshell:~/picoCTF2024/time_machine/drop-in$ cat message.txt 
This is what I was working on, but I'd need to look at my commit history to know why...
elyahir-picoctf@webshell:~/picoCTF2024/time_machine/drop-in$ 
elyahir-picoctf@webshell:~/picoCTF2024/time_machine/drop-in$ git show

commit 89d296ef533525a1378529be66b22d6a2c01e530 (HEAD -> master)
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:07:22 2024 +0000

    picoCTF{t1m3m@ch1n3_186cd7d7}

diff --git a/message.txt b/message.txt
new file mode 100644
index 0000000..4324621
--- /dev/null
+++ b/message.txt
@@ -0,0 +1 @@
+This is what I was working on, but I'd need to look at my commit history to know why...
\ No newline at end of file
(END)
```

## Notas adicionales


## Referencias

