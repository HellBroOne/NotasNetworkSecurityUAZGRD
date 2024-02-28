# Level 5
## Objetivo
The password for the next level is stored in the only human-readable file in the **inhere** directory. Tip: if your terminal is messed up, try the “reset” command.

La contraseña para el siguiente nivel se almacena en el único archivo legible por humanos en el directorio interno. Consejo: si tu terminal está estropeado, prueba el comando “reset”.
### Datos de Acceso al nivel
Comandos: [ls](https://man7.org/linux/man-pages/man1/ls.1.html) , [cd](https://man7.org/linux/man-pages/man1/cd.1p.html) , [cat](https://man7.org/linux/man-pages/man1/cat.1.html) , [file](https://man7.org/linux/man-pages/man1/file.1.html) , du , find
Usuario: bandit4
Contraseña: *lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR* (Descubierta)
Servidor: bandit.labs.overthewire.org
Puerto: 2220
### Solución
(Después de haber hecho lo del nivel 4)
```
bandit4@bandit:~$ ls
inhere
bandit4@bandit:~$ cd inhere/
bandit4@bandit:~/inhere$ ls
-file00  -file01  -file02  -file03  -file04  -file05  -file06  -file07  -file08  -file09
bandit4@bandit:~/inhere$ cat ./-file00
QRrtZ�i�        �H
                  |��ȧ����^��bandit4@bandit:~/inhere$ file ./-file00
./-file00: data
bandit4@bandit:~/inhere$ file ./*
./-file00: data
./-file01: data
./-file02: data
./-file03: data
./-file04: data
./-file05: data
./-file06: data
./-file07: ASCII text
./-file08: data
./-file09: data
bandit4@bandit:~/inhere$ cat ./-file07
lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR
bandit4@bandit:~/inhere$ exit
logout
Connection to bandit.labs.overthewire.org closed.

C:Users/User> ssh bandit5@bandit.labs.overthewire.org -p 2220
Enter password: lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR
```
### Notas Adicionales
Con este nivel pudimos comprender las funcionalidades del comando "file", el cuál nos permite mostrar el tipo de un archivo o archivos si lo aplicamos a un directorio.
**file**: Muestra de qué tipo es un archivo.
### Referencias
https://overthewire.org/wargames/bandit/bandit5.html