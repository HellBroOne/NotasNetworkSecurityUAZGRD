# Level 6
## Objetivo
The password for the next level is stored **somewhere on the server** and has all of the following properties:
- owned by user bandit7.
- owned by group bandit6.
- 33 bytes in size.

La contraseña para el siguiente nivel se almacena en algún lugar del servidor y tiene todas las propiedades siguientes:
- propiedad del usuario bandit7.
- propiedad del grupo bandit6.
- 33 bytes de tamaño.
### Datos de Acceso al nivel
Comandos: [ls](https://man7.org/linux/man-pages/man1/ls.1.html) , [cd](https://man7.org/linux/man-pages/man1/cd.1p.html) , [cat](https://man7.org/linux/man-pages/man1/cat.1.html) , [file](https://man7.org/linux/man-pages/man1/file.1.html) , du , find
Usuario: bandit6
Contraseña: *z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S* (Descubierta)
Servidor: bandit.labs.overthewire.org
Puerto: 2220
### Solución
(Después de haber hecho lo del nivel 6)
```
bandit6@bandit:~$ dir
bandit6@bandit:~$ ls
bandit6@bandit:~$ ls -la
total 20
drwxr-xr-x  2 root root 4096 Oct  5 06:19 .
drwxr-xr-x 70 root root 4096 Oct  5 06:20 ..
-rw-r--r--  1 root root  220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root root 3771 Jan  6  2022 .bashrc
-rw-r--r--  1 root root  807 Jan  6  2022 .profile
bandit6@bandit:~$  find / -user bandit7 -group bandit6 -size 33c 2>/dev/null
/var/lib/dpkg/info/bandit7.password
bandit6@bandit:~$ cat /var/lib/dpkg/info/bandit7.password
z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S
bandit6@bandit:~$ exit
logout
Connection to bandit.labs.overthewire closed.

C:Users/User> ssh bandit7@bandit.labs.overthewire.org -p 2220
Enter password: z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S
```
### Notas Adicionales
Para este nivel volvimos a usar find, sin embargo, ahora buscamos bajo ciertas opciones de búsqueda específicas, como la opción de -user y -group.
*-user*: opción de find que permite buscar a un archivo de un usuario específico.
*-group*: opción de find que permite buscar a un archivo que este compartido con un grupo específico.
### Referencias
https://overthewire.org/wargames/bandit/bandit7.html