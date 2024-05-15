# Level 2
## Objetivo
The password for the next level is stored in a file called **-** located in the home directory

La contraseña para el siguiente nivel se almacena en un archivo llamado - ubicado en el directorio de inicio.
### Datos de Acceso al nivel
Comandos: [ls](https://man7.org/linux/man-pages/man1/ls.1.html) , [cd](https://man7.org/linux/man-pages/man1/cd.1p.html) , [cat](https://man7.org/linux/man-pages/man1/cat.1.html) , [file](https://man7.org/linux/man-pages/man1/file.1.html) , du , find
Usuario: bandit1
Contraseña: *rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi* (Descubierta)
Servidor: bandit.labs.overthewire.org
Puerto: 2220
### Solución
(Después de haber hecho lo del nivel 1)
```
bandit1@bandit:~$ ls
-
bandit1@bandit:~$ cat -
^C
bandit1@bandit:~$ cd -
-bash: cd: OLDPWD not set
bandit1@bandit:~$ cat ./-
rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi
bandit1@bandit:~$ pwd
/home/bandit1
bandit1@bandit:~$ cat /home/bandit1/-
rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi
bandit1@bandit:~$ exit
logout
Connection to bandit.labs.overthewire closed.

C:Users/User> ssh bandit2@bandit.labs.overthewire.org -p 2220
Enter password: rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi
```
### Notas Adicionales
En este nivel aprendimos a como acceder a archivos de directorios desde un solo comando usando rutas relativas y que también se pueden aplicar usando rutas absolutas. Asimismo, se pudo utilizar el comando pwd que muestra la ruta del directorio en el que estamos actualmente. 
**pwd**: devuelve la ruta en la que estamos situados actualmente.
### Referencias
https://overthewire.org/wargames/bandit/bandit2.html