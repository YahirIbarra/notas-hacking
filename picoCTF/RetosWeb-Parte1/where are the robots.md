## Objetivo
Can you find the robots? `https://jupiter.challenges.picoctf.org/problem/60915/` ([link](https://jupiter.challenges.picoctf.org/problem/60915/)) or http://jupiter.challenges.picoctf.org:60915

## Pistas
- What part of the website could tell you where the creator doesn't want you to look?

## Solución
```
1. Acceder a robots.txt
https://jupiter.challenges.picoctf.org/problem/60915/robots.txt

User-agent: *
Disallow: /8028f.html

2. Entrar a la url desactivada
https://jupiter.challenges.picoctf.org/problem/60915/8028f.html

Guess you found the robots
picoCTF{ca1cu1at1ng_Mach1n3s_8028f}
```

## Notas adicionales
- El archivo robots.txt contiene información de la indexación de la pagina (como paginas a donde se desea que ningún usuario vaya)

## Referencias

