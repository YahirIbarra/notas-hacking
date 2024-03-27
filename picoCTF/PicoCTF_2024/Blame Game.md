## Objetivo
Someone's commits seems to be preventing the program from working. Who is it?You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/156/challenge.zip)

## Pistas
- In collaborative projects, many users can make many changes. How can you see the changes within one file?
- Read the chapter on Git from the picoPrimer [here](https://primer.picoctf.org/#_git_version_control).
- You can use `python3 <file>.py` to try running the code, though you won't need to for this challenge.

## Solución
```
elyahir-picoctf@webshell:~/picoCTF2024/blame_game$ cd drop-in/
elyahir-picoctf@webshell:~/picoCTF2024/blame_game/drop-in$ ls
message.py
elyahir-picoctf@webshell:~/picoCTF2024/blame_game/drop-in$ cat message.py 
print("Hello, World!"
elyahir-picoctf@webshell:~/picoCTF2024/blame_game/drop-in$ cd .git/
elyahir-picoctf@webshell:~/picoCTF2024/blame_game/drop-in/.git$ ls
COMMIT_EDITMSG  HEAD  branches  config  description  hooks  index  info  logs  objects  refs
elyahir-picoctf@webshell:~/picoCTF2024/blame_game/drop-in/.git$ cd logs/
elyahir-picoctf@webshell:~/picoCTF2024/blame_game/drop-in/.git/logs$ ls
HEAD  refs
elyahir-picoctf@webshell:~/picoCTF2024/blame_game/drop-in/.git/logs$ cat HEAD | grep "picoCTF{"
c9e851509190f5887e91339ee18087e3e77ebfda 0351e0474493168ca76441c24630c17554fd09ca picoCTF{@sk_th3_1nt3rn_d2d29f22} <ops@picoctf.com> 1710202021 +0000   commit: optimize file size of prod code
```

## Notas adicionales


## Referencias

