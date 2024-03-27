## Objetivo

People keep trying to trick my players with imitation flags. I want to make sure they get the real thing! I'm going to provide the SHA-256 hash and a decrypt script to help you know that my flags are legitimate.You can download the challenge files here:

- `[challenge.zip](https://artifacts.picoctf.net/c_rhea/20/challenge.zip)`

The same files are accessible via SSH here:`ssh -p 53841 ctf-player@rhea.picoctf.net`Using the password `f3b61b38`. Accept the fingerprint with `yes`, and `ls` once connected to begin. Remember, in a shell, passwords are hidden!

- Checksum: fba9f49bf22aa7188a155768ab0dfdc1f9b86c47976cd0f7c9003af2e20598f7
- To decrypt the file once you've verified the hash, run `./decrypt.sh files/<file>`.
## Solución

```
Conectarse via ssh
Usar el siguiente comando sha256sum files/* | grep fba9f49bf22aa7188a155768ab0dfdc1f9b86c47976cd0f7c9003af2e20598f7
con eso verificamos que archivo tiene el mismo checksum que el archivo original
Cuando tengamos el archivo ejecutamos ./decrypt.sh files/87590c24
donde files/87590c24 es el archivo que coincidio con el checksum
flag: picoCTF{trust_but_verify_87590c24}
```  

## Notas adicionales

**sha256sum** es un comando en Linux que se utiliza para calcular el valor hash SHA-256 de un archivo.

## Referencias

[https://man.archlinux.org/man/sha256sum.1.es]