## Objetivo
I just recently learnt about the SRA public key cryptosystem... or wait, was it supposed to be RSA? Hmmm, I should probably check...

Connect to the program on our server: `nc saturn.picoctf.net 54688`Download the program: [chal.py](https://artifacts.picoctf.net/c/298/chal.py)

## Pistas


## Solución
```
* CREAR UN SCRIPT PARA PODER DESCRIFRAR EL ENCRIPTADO USANDO TODAS LAS COMBINACIONES DE FACTORES *

┌──(kali㉿kali)-[~/Documents/Retos/sra]
└─$ nano exploit.py

from pwn import *
import primefac
from itertools import combinations
from Crypto.Util.number import long_to_bytes

#Funcion que genera todas las sublistas
def sub_lists(l):
        #inicializando lista vacia
        comb = []

        #Iterando hasta la longitud de la lista
        for i in range(1, len(l)+1):
                #Generando una sublista
                comb += [list(j) for j in combinations(l, i)]
        #Regresando lista
        return comb

def divisors(phi):
        print("Dame los divisores de", phi-1)
        return(eval(input()))

#Conexion con el servidor
r = remote('saturn.picoctf.net', 55813)
#Obtener el texto cifrado
r.recvuntil("anger =")
ciphertext = int(r.recvline())
#Obtener d
r.recvuntil("envy =")
d = int(r.recvline())
print("cipher=", ciphertext)
print("d=", d)
print(r.recvuntil("vainglory?"))
r.recvline()
#Desde d es e^-1 mod (p-1)*(q-1), d*e=k*(p-1)*(q-1)+1
#Asi (p-1)*(q-1)*k = d*e-1
factors = divisors(d*65537)
combos = sub_lists(factors)
primes = set()
#Intenta todas las posibles sublistas de factores para los factores de (p-1)
for l in combos:
        product = 1
        #Multiplicarlos entre ellos para obtener p-1
        for k in l:
                product = product * k
        #Si la longitud correcta y sumar 1 da un numero primo, entonces tal vez
        if product.bit_length()==128 and primefac.isprime(product+1):
                primes.add(product+1)
print(primes)
primelist = list(primes)
#Intenta todos los posibles pares de primos
for p in primelist:
        for q in primelist:
                n=p*q
                #Decodificar con el posible n
                plain = pow(ciphertext, d, n)
                try:
                        plaintext = long_to_bytes(plain)
                        #Ver si corresponde al texto y de ser asi, intentarlo
                        print(plaintext.decode())
                        r.sendline(plaintext.decode())
                        print(r.recvline())
                        print(r.recvline())
                        print(r.recvline())
                except:
                        continue

* EJECUTAR EL SCRIPT Y OBTENER LA DESCOMPOSICION DE FACTORES PRIMOS *

┌──(kali㉿kali)-[~/Documents/Retos/sra]
└─$ python3 exploit.py
[+] Opening connection to saturn.picoctf.net on port 55813: Done
/home/kali/Documents/Retos/sra/exploit.py:25: BytesWarning: Text is not bytes; assuming ASCII, no guarantees. See https://docs.pwntools.com/#bytes
  r.recvuntil("anger =")
/home/kali/Documents/Retos/sra/exploit.py:28: BytesWarning: Text is not bytes; assuming ASCII, no guarantees. See https://docs.pwntools.com/#bytes
  r.recvuntil("envy =")
cipher= 85466928578437837734974681544761216813706785844629927197283639590289117567481
d= 74669337945986017503721579991033121875179780983920845018811163475884964231025
/home/kali/Documents/Retos/sra/exploit.py:32: BytesWarning: Text is not bytes; assuming ASCII, no guarantees. See https://docs.pwntools.com/#bytes
  print(r.recvuntil("vainglory?"))
b'vainglory?'
Dame los divisores de 4893604400966085629141401187872337708333657306343220419997827220719072900808685424
[2, 2, 2, 2, 3, 3, 7, 11, 47, 347, 2137, 6563, 136033, 156677, 667013, 604375979366977266261487, 224569289535376035237123547]
{265109274082281005679021054081913121803, 240692530023022569100986563358247206013, 232765466804431717938862336303715737777, 330986076103751969572295135620743662039, 184812918073394480550235466331846426953, 288529812224483432031280371173623458457, 321824193445776814575743387562430337929, 194643392439000569941205437945242513493, 172347499166463738995217634441513107127, 208426703800540011945331286739732052717}
GpJGtBg16YvDEFdt
/home/kali/Documents/Retos/sra/exploit.py:60: BytesWarning: Text is not bytes; assuming ASCII, no guarantees. See https://docs.pwntools.com/#bytes
  r.sendline(plaintext.decode())
b'> GpJGtBg16YvDEFdt\r\n'
b'Conquered!\r\n'
b'picoCTF{7h053_51n5_4r3_n0_m0r3_b2f9b414}\r\n'
GpJGtBg16YvDEFdt
[*] Closed connection to saturn.picoctf.net port 55813


Flag: picoCTF{7h053_51n5_4r3_n0_m0r3_b2f9b414}
```

## Notas adicionales


## Referencias
- https://www.dcode.fr/prime-factors-decomposition
