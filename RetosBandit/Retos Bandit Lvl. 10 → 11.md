# Level 10
## Objetivo
The password for the next level is stored in the file **data.txt**, which contains base64 encoded data.

La contraseña para el siguiente nivel se almacena en el archivo **data.txt**, que contiene datos codificados en base64..
### Datos de Acceso al nivel
Comandos: grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd
Usuario: bandit10
Contraseña: *6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM* 
Servidor: bandit.labs.overthewire.org
Puerto: 2220
### Solución
(Después de haber hecho lo del nivel 10)
```
bandit10@bandit:~$ ls
data.txt
bandit10@bandit:~$ cat data.txt
VGhlIHBhc3N3b3JkIGlzIDZ6UGV6aUxkUjJSS05kTllGTmI2blZDS3pwaGxYSEJNCg==
bandit10@bandit:~$ echo "hola que tal" | base64
aG9sYSBxdWUgdGFsCg==
bandit10@bandit:~$ base64 -d data.txt
The password is 6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM
bandit10@bandit:~$ exit
logout
Connection to bandit.labs.overthewire.org closed.

C:Users/User> ssh bandit11@bandit.labs.overthewire.org -p 2220
Enter password: 6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM
```
### Notas Adicionales
Para este nivel usamos codificaciones en base 64, esto con el comando de base 64 para encriptar y la opción -d para desencriptar al archivo data.txt .
### Referencias
https://overthewire.org/wargames/bandit/bandit11.html