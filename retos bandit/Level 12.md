## Objetivo
The password for the next level is stored in the file **data.txt**, which is a hexdump of a file that has been repeatedly compressed. For this level it may be useful to create a directory under /tmp in which you can work using mkdir. For example: mkdir /tmp/myname123. Then copy the datafile using cp, and rename it using mv (read the manpages!)

## Datos de acceso al nivel
**bandit.labs.overthewire.org**
bandit12
JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv
## Solución
```
bandit12@bandit:~$ mkdir /tmp/dir2
bandit12@bandit:~$ cp ~/data.txt ./data.txt
cp: '/home/bandit12/data.txt' and './data.txt' are the same file
bandit12@bandit:~$ cp ~/data.txt ./
cp: '/home/bandit12/data.txt' and './data.txt' are the same file
bandit12@bandit:~$ ls
data.txt
bandit12@bandit:~$ cp data.txt /tmp/dir2
bandit12@bandit:~$ cd /tmp/dir2
bandit12@bandit:/tmp/dir2$ cat data.txt | xxd -r > data
bandit12@bandit:/tmp/dir2$ ls
data  data.txt
bandit12@bandit:/tmp/dir2$ file data
data: gzip compressed data, was "data2.bin", last modified: Thu Oct  5 06:19:20 2023, max compression, from Unix, original size modulo 2^32 573
bandit12@bandit:/tmp/dir2$ mv data data.gzip
bandit12@bandit:/tmp/dir2$ ls
data.gzip  data.txt
bandit12@bandit:/tmp/dir2$ gzip -d data.gzip
gzip: data.gzip: unknown suffix -- ignored
bandit12@bandit:/tmp/dir2$ mp data.gzip data2.gz
Command 'mp' not found, but can be installed with:
apt install multiplex
Please ask your administrator.
bandit12@bandit:/tmp/dir2$ mv data.gzip data2.gz
bandit12@bandit:/tmp/dir2$ gzip -d data.gz
gzip: data.gz: No such file or directory
bandit12@bandit:/tmp/dir2$ gzip -d data2.gz
bandit12@bandit:/tmp/dir2$ ls
data2  data.txt
bandit12@bandit:/tmp/dir2$ file data2
data2: bzip2 compressed data, block size = 900k
bandit12@bandit:/tmp/dir2$ mv data2 data3.bz
bandit12@bandit:/tmp/dir2$ bzip2 -d data3.bz
bandit12@bandit:/tmp/dir2$ ls
data3  data.txt
bandit12@bandit:/tmp/dir2$ file data3
data3: gzip compressed data, was "data4.bin", last modified: Thu Oct  5 06:19:20 2023, max compression, from Unix, original size modulo 2^32 20480
bandit12@bandit:/tmp/dir2$ mv data3 data4.gz
bandit12@bandit:/tmp/dir2$ gzip -d data3.gz
gzip: data3.gz: No such file or directory
bandit12@bandit:/tmp/dir2$ gzip -d data4.gz
bandit12@bandit:/tmp/dir2$ ls
data4  data.txt
bandit12@bandit:/tmp/dir2$ file data4
data4: POSIX tar archive (GNU)
bandit12@bandit:/tmp/dir2$ mv data4 data5.tar
bandit12@bandit:/tmp/dir2$ tar -xf data5.tar
bandit12@bandit:/tmp/dir2$ ls
data5.bin  data5.tar  data.txt
bandit12@bandit:/tmp/dir2$ file data5.bin
data5.bin: POSIX tar archive (GNU)
bandit12@bandit:/tmp/dir2$ mv data5.bin data6.tar
bandit12@bandit:/tmp/dir2$ tar -xf data6.tar
bandit12@bandit:/tmp/dir2$ ls
data5.tar  data6.bin  data6.tar  data.txt
bandit12@bandit:/tmp/dir2$ file data.bin
data.bin: cannot open `data.bin' (No such file or directory)
bandit12@bandit:/tmp/dir2$ file dat6a.bin
dat6a.bin: cannot open `dat6a.bin' (No such file or directory)
bandit12@bandit:/tmp/dir2$ file data6.bin
data6.bin: bzip2 compressed data, block size = 900k
bandit12@bandit:/tmp/dir2$ mv data6.bin data6.bz
bandit12@bandit:/tmp/dir2$ bzip2 -d data6.bz
bandit12@bandit:/tmp/dir2$ ls
data5.tar  data6  data6.tar  data.txt
bandit12@bandit:/tmp/dir2$ cat data6
data8.bin0000644000000000000000000000011714507452550011255 0ustar  rootroohUedata9.binHU(H,../JQ,V(O
Oqp,2qNtIH,-7+(-r)uG1bandit12@bandit:/tmp/dir2$ file data6
data6: POSIX tar archive (GNU)
bandit12@bandit:/tmp/dir2$ mv data6 data7.tar
bandit12@bandit:/tmp/dir2$ tar -xf data7.tar
bandit12@bandit:/tmp/dir2$ ls
data5.tar  data6.tar  data7.tar  data8.bin  data.txt
bandit12@bandit:/tmp/dir2$ tar -xf data7.tar
bandit12@bandit:/tmp/dir2$ ls
data5.tar  data6.tar  data7.tar  data8.bin  data.txt
bandit12@bandit:/tmp/dir2$ file data8.bin
data8.bin: gzip compressed data, was "data9.bin", last modified: Thu Oct  5 06:19:20 2023, max compression, from Unix, original size modulo 2^32 49
bandit12@bandit:/tmp/dir2$ mv data8.bin data9.gz
bandit12@bandit:/tmp/dir2$ gzip -d data8.gz
gzip: data8.gz: No such file or directory
bandit12@bandit:/tmp/dir2$ gzip -d data9.gz
bandit12@bandit:/tmp/dir2$ ls
data5.tar  data6.tar  data7.tar  data9  data.txt
bandit12@bandit:/tmp/dir2$ file data9
data9: ASCII text
bandit12@bandit:/tmp/dir2$ cat data9
The password is wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw
bandit12@bandit:/tmp/dir2$ exit
```

## Notas adicionales
- El comando *xxd* con el parametro -r hace reversa del cifrado hexadecimal
- Los comandos de compresion comunmente usan el parametro -d para extraer (excepto el tar, ya que usa -xf)
- El comando file nos permite conocer que tipo de archivo es el que se esta manejando
- El comando mv nos permite renombrar archivos

## Referencias
- https://en.wikipedia.org/wiki/Hex_dump
- https://medium.com/secttp/overthewire-bandit-level-12-439f655f6fd5
