# Level 3
## Objetivo
The password for the next level is stored in a file called **spaces in this filename** located in the home directory

La contraseña para el siguiente nivel se almacena en un archivo llamado **spaces in this filename** (espacios en este nombre de archivo) ubicado en el directorio de inicio.
### Datos de Acceso al nivel
Comandos: [ls](https://man7.org/linux/man-pages/man1/ls.1.html) , [cd](https://man7.org/linux/man-pages/man1/cd.1p.html) , [cat](https://man7.org/linux/man-pages/man1/cat.1.html) , [file](https://man7.org/linux/man-pages/man1/file.1.html) , du , find
Usuario: bandit2
Contraseña: *aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG* (Descubierta)
Servidor: bandit.labs.overthewire.org
Puerto: 2220
### Solución
(Después de haber hecho lo del nivel 2)
```
bandit2@bandit:~$ ls
spaces in this filename
bandit2@bandit:~$ ls
spaces in this filename
bandit2@bandit:~$ cat spaces in this filename
cat: spaces: No such file or directory
cat: in: No such file or directory
cat: this: No such file or directory
cat: filename: No such file or directory
bandit2@bandit:~$ cat "spaces in this filename"
aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG
bandit2@bandit:~$ exit
logout
Connection to bandit.labs.overthewire.org closed.

C:Users/User> ssh bandit3@bandit.labs.overthewire.org -p 2220
Enter password: aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG
```
### Notas Adicionales
En este nivel aprendimos a como hacer referencia a archivos con espacios en sus nombres de archivos, para ello, se usan las dobles comillas (") para poder colocar dentro de las comillas el nombre del archivo.
### Referencias
https://overthewire.org/wargames/bandit/bandit3.html