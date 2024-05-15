# Level 12
## Objetivo
The password for the next level is stored in the file data.txt, which is a hexdump of a file that has been repeatedly compressed. For this level it may be useful to create a directory under /tmp in which you can work using mkdir. For example: mkdir /tmp/myname123. Then copy the datafile using cp, and rename it using mv (read the manpages!).

La contraseña para el siguiente nivel se almacena en el archivo data.txt, que es un volcado hexadecimal de un archivo que se ha comprimido repetidamente. Para este nivel puede resultar útil crear un directorio en /tmp en el que pueda trabajar utilizando mkdir. Por ejemplo: mkdir /tmp/minombre123. Luego copie el archivo de datos usando cp y cámbiele el nombre usando mv (¡lea las páginas de manual!).
### Datos de Acceso al nivel
Comandos: grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd, mkdir, cp, mv, file
Usuario: bandit12
Contraseña: *wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw* 
Servidor: bandit.labs.overthewire.org
Puerto: 2220
### Solución
(Después de haber hecho lo del nivel 12)
```
bandit12@bandit:~$ ls
data.txt
bandit12@bandit:~$ xxd -r data.txt | file -
/dev/stdin: gzip compressed data, was "data2.bin", last modified: Thu Oct  5 06:19:20 2023, max compression, from Unix
bandit12@bandit:~$ xxd -r data.txt | zcat | file -
/dev/stdin: bzip2 compressed data, block size = 900k
bandit12@bandit:~$ xxd -r data.txt | zcat | bzcat | file -
/dev/stdin: gzip compressed data, was "data4.bin", last modified: Thu Oct  5 06:19:20 2023, max compression, from Unix
bandit12@bandit:~$ xxd -r data.txt | zcat | bzcat | zcat |
file -
/dev/stdin: POSIX tar archive (GNU)
bandit12@bandit:~$ xxd -r data.txt | zcat | bzcat | zcat | tar x0 | file -
tar: Options '-[0-7][lmh]' not supported by *this* tar
Try 'tar --help' or 'tar --usage' for more information.
/dev/stdin: empty
bandit12@bandit:~$ xxd -r data.txt | zcat | bzcat | zcat | tar xO | file -
/dev/stdin: POSIX tar archive (GNU)
bandit12@bandit:~$ xxd -r data.txt | zcat | bzcat | zcat | tar xO | tar xO | file -
/dev/stdin: bzip2 compressed data, block size = 900k
bandit12@bandit:~$ xxd -r data.txt | zcat | bzcat | zcat | tar xO | tar xO | bzcat | file -
/dev/stdin: POSIX tar archive (GNU)
bandit12@bandit:~$ xxd -r data.txt | zcat | bzcat | zcat | tar xO | tar xO | bzcat | tar xO | file -
/dev/stdin: gzip compressed data, was "data9.bin", last modified: Thu Oct  5 06:19:20 2023, max compression, from Unix
bandit12@bandit:~$ xxd -r data.txt | zcat | bzcat | zcat | tar xO | tar xO | bzcat | tar xO | zcat | file -
/dev/stdin: ASCII text
bandit12@bandit:~$ xxd -r data.txt | zcat | bzcat | zcat | tar xO | tar xO | bzcat | tar xO | zcat
The password is wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw
bandit12@bandit:~$ exit
logout
Connection to bandit.labs.overthewire.org closed.

C:Users/User> ssh bandit13@bandit.labs.overthewire.org -p 2220
Enter password: wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw
```
### Notas Adicionales
Para este nivel comprendimos los formatos de compresión usados en linux, para poder descomprimir un archivo comprimido varias veces por varios formatos. Dichos formatos son los siguientes:
```
Algunos tipos de compresion en Linux
-----------------------------------------------------
ext  comp     desc                  ver en consola
-----------------------------------------------------
.gz  gzip     gzip -d (gunzip)      zcat
.bz2 bzip2    bzip2 -d (bunzip2)    bzcat
.tar tar      tar xf                tar xO
----------------------------------------------------
otros (hay que instalar) :
.zip zip      unzip (7z x)
.rar rar      unrar (7z x)
```
dichos formatos necesitaron sus comandos en consola como los fueron:
**zcat:** descomprimir gzip.
**bzcat:** descomprimir bzip2.
**tar xO:** descomprimir tar (es una letra "O" en lugar de un número "0").
### Referencias
https://overthewire.org/wargames/bandit/bandit13.html