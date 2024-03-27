## Objetivo

Can you handle APKs?Download the android apk [here](https://artifacts.picoctf.net/c_titan/140/mobpsycho.apk).

## Solución

```
Cambiar la extension del apk a zip
Desempaquetar el archivo haciendo grep a la salida para buscar el archivo flag
Hacer un cat al archivo, pero como la bandera esta en formato hexadecimal debemos hacer un pipe a la salida con el comando xxd -r -p
flag: picoCTF{ax8mC0RU6ve_NX85l4ax8mCl_5e67ea5e}
```

## Notas adicionales

El comando **xxd** con la opción **-p** nos ayuda a trabajar con hexadecimales y con la opción **-r** indica que queremos revertir el proceso.
## Referencias