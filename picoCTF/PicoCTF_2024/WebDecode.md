## Objetivo
Do you know how to use the web inspector?Start searching [here](http://titan.picoctf.net:53646/) to find the flag

## Pistas
The flag may or may not be encoded.

## Solución
1. Abrir el enlace e inspeccionarlo con las herramientas de desarrollador.
2. En la página web, ir a la sección de About.
3. Ir a Sources y después a about.hml, donde se encuentra la siguiente parte:
```
<section class="about" notify_true="cGljb0NURnt3ZWJfc3VjYzNzc2Z1bGx5X2QzYzBkZWRfMjgzZTYyZmV9">
```
4. Copiar `cGljb0NURnt3ZWJfc3VjYzNzc2Z1bGx5X2QzYzBkZWRfMjgzZTYyZmV9` e ir a cyberchef.
5. Se decodifica en base64.
6. La bandera es :
picoCTF{web_succ3ssfully_d3c0ded_283e62fe}
## Notas adicionales

## Referencias
