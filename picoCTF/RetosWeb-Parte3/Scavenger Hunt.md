## Objetivo
There is some interesting information hidden around this site [http://mercury.picoctf.net:5080/](http://mercury.picoctf.net:5080/). Can you find it?

## Pistas
- You should have enough hints to find the files, don't run a brute forcer.

## Solución
```
Primera parte en el html:
</p>
	<!-- Here's the first part of the flag: picoCTF{t -->
      </div>

Segunda parte en css:
/* CSS makes the page look nice, and yes, it also has part of the flag. Here's part 2: h4ts_4_l0 */

Tercera parte en js:
/* How can I keep Google from indexing my website? */

Tercera parte en robots:
http://mercury.picoctf.net:5080/robots.txt
User-agent: *
Disallow: /index.html
# Part 3: t_0f_pl4c
# I think this is an apache server... can you Access the next flag?

Cuarta parte en .htaccess:
# Part 4: 3s_2_lO0k
# I love making websites on my Mac, I can Store a lot of information there.

Quinta parte en .DS_Store:
Congrats! You completed the scavenger hunt. Part 5: _35844447}

Resultado: picoCTF{th4ts_4_l0t_0f_pl4c3s_2_lO0k_35844447}
```

## Notas adicionales
- En apache hay un archivo que controla el acceso de usuarios, el cual es el archivo .htaccess
- En Mac hay un archivo que guarda informacion, el cual es .DS_Store

## Referencias

