# Level 4
## Objetivo
The password for the next level is stored in a hidden file in the **inhere** directory.

La contraseña para el siguiente nivel se almacena en un archivo oculto en el directorio interno.
### Datos de Acceso al nivel
Comandos: [ls](https://man7.org/linux/man-pages/man1/ls.1.html) , [cd](https://man7.org/linux/man-pages/man1/cd.1p.html) , [cat](https://man7.org/linux/man-pages/man1/cat.1.html) , [file](https://man7.org/linux/man-pages/man1/file.1.html) , du , find
Usuario: bandit3
Contraseña: *2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe* (Descubierta)
Servidor: bandit.labs.overthewire.org
Puerto: 2220
### Solución
(Después de haber hecho lo del nivel 3)
```
bandit3@bandit:~$ ls
inhere
bandit3@bandit:~$ cat inhere
cat: inhere: Is a directory
bandit3@bandit:~$ cd inhere
bandit3@bandit:~/inhere$ ls
bandit3@bandit:~/inhere$ ls -la
total 12
drwxr-xr-x 2 root    root    4096 Oct  5 06:19 .
drwxr-xr-x 3 root    root    4096 Oct  5 06:19 ..
-rw-r----- 1 bandit4 bandit3   33 Oct  5 06:19 .hidden
bandit3@bandit:~/inhere$ cat .hidden
2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe
bandit3@bandit:~/inhere$ exit
logout
Connection to bandit.labs.overthewire.org closed.

C:Users/User> ssh bandit4@bandit.labs.overthewire.org -p 2220
Enter password: 2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe
```
### Notas Adicionales
Con esta práctica se pudo completar el aprendizaje de manipulación de archivos ocultos en linux, mostrando los elementos con ls pero utilizando la opción de "l" y "a", cada opción muestra una cosa diferente:
*-l*: Menos l (de list) muestra a detalle un listado de los archivos, es así como se nos permite obtener tanto los permisos y la fecha de archivos
*-a: Menos a (de all), muestra todos los archivos sin ninguna excepción.
### Referencias
https://overthewire.org/wargames/bandit/bandit4.html