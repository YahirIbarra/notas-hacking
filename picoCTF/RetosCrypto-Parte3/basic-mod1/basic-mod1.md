## Objetivo
We found this weird message being passed around on the servers, we think we have a working decryption scheme.Download the message [here](https://artifacts.picoctf.net/c/128/message.txt).Take each number mod 37 and map it to the following character set: 0-25 is the alphabet (uppercase), 26-35 are the decimal digits, and 36 is an underscore.Wrap your decrypted message in the picoCTF flag format (i.e. `picoCTF{decrypted_message}`)

## Pistas
- Do you know what `mod 37` means?
- `mod 37` means modulo 37. It gives the remainder of a number after being divided by 37.

## Solución
```
┌──(kali㉿kali)-[~/Documents/Retos/basic-mod1]
└─$ ls 
message.txt
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/basic-mod1]
└─$ cat message.txt           
165 248 94 346 299 73 198 221 313 137 205 87 336 110 186 69 223 213 216 216 177 138  
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/basic-mod1]
└─$ nano script.py
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/basic-mod1]
└─$ cat script.py                                                                    
datos = open("message.txt").read().split()

flag = ""

for n in datos:
        r = int(n) % 37
        if(r >= 0 and r <= 25):
                s = chr(r+65)
                flag += s
        elif(r >= 26 and r <= 35):
                s = chr(r+22)
                flag += s
        else:
                s = "_"
                flag += s

print("picoCTF{"+flag+"}")
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/basic-mod1]
└─$ python3 script.py
picoCTF{R0UND_N_R0UND_B6B25531}
```

## Notas adicionales


## Referencias


