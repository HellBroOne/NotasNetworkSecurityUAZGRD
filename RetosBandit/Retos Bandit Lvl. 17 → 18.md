# Level 17
## Objetivo
There are 2 files in the homedirectory: **passwords.old and passwords.new**. The password for the next level is in **passwords.new** and is the only line that has been changed between **passwords.old and passwords.new**
**NOTE: if you have solved this level and see ‘Byebye!’ when trying to log into bandit18, this is related to the next level, bandit19**.

Hay 2 archivos en el directorio de inicio: **passwords.old y passwords.new**. La contraseña para el siguiente nivel está en **passwords.new** y es la única línea que se ha cambiado entre **passwords.old y passwords.new**.
**NOTA: si has resuelto este nivel y ves "Byebye!" al intentar iniciar sesión en bandit18, esto está relacionado con el siguiente nivel, bandit19.**
### Datos de Acceso al nivel
Comandos: cat, grep, ls, diff
Usuario: bandit17
Contraseña:  *VwOSWtCA7lRKkTfbr2IDh6awj9RNZM5e* (Nivel 17), *hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg* (Nivel 18)
Servidor: bandit.labs.overthewire.org
Puerto: 2220
### Solución
(Después de haber hecho lo del nivel 17)
```
bandit17@bandit:~$ ls -la
total 36
drwxr-xr-x  3 root     root     4096 Oct  5 06:19 .
drwxr-xr-x 70 root     root     4096 Oct  5 06:20 ..
-rw-r-----  1 bandit17 bandit17   33 Oct  5 06:19 .bandit16.password
-rw-r--r--  1 root     root      220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root     root     3771 Jan  6  2022 .bashrc
-rw-r-----  1 bandit18 bandit17 3300 Oct  5 06:19 passwords.new
-rw-r-----  1 bandit18 bandit17 3300 Oct  5 06:19 passwords.old
-rw-r--r--  1 root     root      807 Jan  6  2022 .profile
drwxr-xr-x  2 root     root     4096 Oct  5 06:19 .ssh
bandit17@bandit:~$ diff passwords.old passwords.new
42c42
< p6ggwdNHncnmCNxuAt0KtKVq185ZU7AW
---
> hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg
bandit17@bandit:~$ diff passwords.old passwords.new --color
42c42
< p6ggwdNHncnmCNxuAt0KtKVq185ZU7AW
---
> hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg
bandit17@bandit:~$ exit
logout
Connection to bandit.labs.overthewire.org closed.

C:Users/User> ssh bandit18@bandit.labs.overthewire.org -p 2220
(Enter password: hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg)
```
### Notas Adicionales
Utilizamos ***diff*** como la utilidad para comparar directorios entre si o ficheros entre sí. La idea es que se nos demuestre que líneas han sido cambiadas en archivos o en directorios.
### Referencias
https://overthewire.org/wargames/bandit/bandit18.html