## Objetivo
In RSA, a small `e` value can be problematic, but what about `N`? Can you decrypt this? [values](https://mercury.picoctf.net/static/b9ddda080c56fb421bf30409bec3460d/values)

## Pistas
- Bits are expensive, I used only a little bit over 100 to save money

## Solución
```
┌──(kali㉿kali)-[~/Documents/Retos/mind_your_ps_and_qs]
└─$ cat values 
Decrypt my super sick RSA:
c: 964354128913912393938480857590969826308054462950561875638492039363373779803642185
n: 1584586296183412107468474423529992275940096154074798537916936609523894209759157543
e: 65537                                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/mind_your_ps_and_qs]
└─$ python3
Python 3.9.8 (main, Nov  7 2021, 15:47:09) 
[GCC 11.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> from Crypto.Util.number import inverse
>>> from Crypto.Util.number import long_to_bytes
>>> c = 964354128913912393938480857590969826308054462950561875638492039363373779803642185
>>> e = 65537
>>> n = 1584586296183412107468474423529992275940096154074798537916936609523894209759157543
>>> p = 2434792384523484381583634042478415057961
>>> q = 650809615742055581459820253356987396346063
>>> n == p*q
True
>>> tn = (p-1)*(q-1)
>>> d = inverse(e,tn)
>>> m = pow(c,d,n)
>>> long_to_bytes(m)
b'picoCTF{sma11_N_n0_g0od_73918962}'
>>> quit()

```

## Notas adicionales


## Referencias

