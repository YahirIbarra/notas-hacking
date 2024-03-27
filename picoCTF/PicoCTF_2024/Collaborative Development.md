## Objetivo
My team has been working very hard on new features for our flag printing program! I wonder how they'll work together?You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/176/challenge.zip)

## Pistas
- `git branch -a` will let you see available branches
- How can file 'diffs' be brought to the main branch? Don't forget to `git config`!
- Merge conflicts can be tricky! Try a text editor like nano, emacs, or vim.

## Solución
```
elyahir-picoctf@webshell:~/picoCTF2024/collaborative_development$ ls
challenge.zip  drop-in
elyahir-picoctf@webshell:~/picoCTF2024/collaborative_development$ cd drop-in/
elyahir-picoctf@webshell:~/picoCTF2024/collaborative_development/drop-in$ ls
flag.py
elyahir-picoctf@webshell:~/picoCTF2024/collaborative_development/drop-in$ cat flag.py 
print("Printing the flag...")
elyahir-picoctf@webshell:~/picoCTF2024/collaborative_development/drop-in$ git branch -a

  feature/part-1
  feature/part-2
  feature/part-3
* main

elyahir-picoctf@webshell:~/picoCTF2024/collaborative_development/drop-in$ git checkout feature/part-1
Switched to branch 'feature/part-1'
elyahir-picoctf@webshell:~/picoCTF2024/collaborative_development/drop-in$ ls
flag.py
elyahir-picoctf@webshell:~/picoCTF2024/collaborative_development/drop-in$ cat flag.py 
print("Printing the flag...")
print("picoCTF{t3@mw0rk_", end='')elyahir-picoctf@webshell:~/picoCTF2024/collaborative_development/drop-in$ git checkout feature/part-2
Switched to branch 'feature/part-2'
elyahir-picoctf@webshell:~/picoCTF2024/collaborative_development/drop-in$ ls
flag.py
elyahir-picoctf@webshell:~/picoCTF2024/collaborative_development/drop-in$ cat flag.py 
print("Printing the flag...")

print("m@k3s_th3_dr3@m_", end='')elyahir-picoctf@webshell:~/picoCTF2024/collaborative_development/drop-in$ git checkout feature/part-3
Switched to branch 'feature/part-3'
elyahir-picoctf@webshell:~/picoCTF2024/collaborative_development/drop-in$ ls
flag.py
elyahir-picoctf@webshell:~/picoCTF2024/collaborative_development/drop-in$ cat flag.py 
print("Printing the flag...")

print("w0rk_2c91ca76}")
elyahir-picoctf@webshell:~/picoCTF2024/collaborative_development/drop-in$


Flag: picoCTF{t3@mw0rk_m@k3s_th3_dr3@m_w0rk_2c91ca76}
```

## Notas adicionales


## Referencias

