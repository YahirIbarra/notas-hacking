## Objetivo
Download this image file and find the flag.

- [Download image file](https://artifacts.picoctf.net/c/101/drawing.flag.svg)

## Pistas


## Solución
```
┌──(kali㉿kali)-[~/…/Retos/segundo_parcial/forensic/enhance]
└─$ open drawing.flag.svg 
                                                                                                                   
┌──(kali㉿kali)-[~/…/Retos/segundo_parcial/forensic/enhance]
└─$ Gtk-Message: 20:51:56.545: Failed to load module "gail"

** (gimp-2.10:12089): WARNING **: 20:51:56.565: (../atk-adaptor/bridge.c:1018):atk_bridge_adaptor_init: runtime check failed: (root)
Gtk-Message: 20:51:57.858: Failed to load module "gail"

** (file-svg:12128): WARNING **: 20:51:57.874: (../atk-adaptor/bridge.c:1018):atk_bridge_adaptor_init: runtime check failed: (root)

                                                                                                                   
┌──(kali㉿kali)-[~/…/Retos/segundo_parcial/forensic/enhance]
└─$ strings  drawing.flag.svg | less
                                                                                                                   
┌──(kali㉿kali)-[~/…/Retos/segundo_parcial/forensic/enhance]
└─$ strings drawing.flag.svg| grep tspan
       id="text3723"><tspan
         id="tspan3748">p </tspan><tspan
         id="tspan3754">i </tspan><tspan
         id="tspan3756">c </tspan><tspan
         id="tspan3758">o </tspan><tspan
         id="tspan3760">C </tspan><tspan
         id="tspan3762">T </tspan><tspan
         id="tspan3764">F { 3 n h 4 n </tspan><tspan
         id="tspan3752">c 3 d _ 2 4 3 7 4 6 7 5 }</tspan></text>


Flag: picoCTF{3nh4nc3d_24374675}

```

## Notas adicionales


## Referencias

