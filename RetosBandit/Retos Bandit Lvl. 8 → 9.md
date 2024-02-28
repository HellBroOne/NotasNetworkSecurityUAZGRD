# Level 8
## Objetivo
The password for the next level is stored in the file **data.txt** and is the only line of text that occurs only once

La contraseña para el siguiente nivel se almacena en el archivo **data.txt** y es la única línea de texto que aparece solo una vez.
### Datos de Acceso al nivel
Comandos: grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd
Usuario: bandit8
Contraseña: *EN632PlfYiZbn3PhVK3XOGSlNInNE00t* (Descubierta)
Servidor: bandit.labs.overthewire.org
Puerto: 2220
### Solución
(Después de haber hecho lo del nivel 8)
```
bandit8@bandit:~$ ls
data.txt
bandit8@bandit:~$ wc data.txt
 1001  1001 33033 data.txt
bandit8@bandit:~$ cat data.txt | sort | uniq -u
EN632PlfYiZbn3PhVK3XOGSlNInNE00t
bandit8@bandit:~$ exit
logout
Connection to bandit.labs.overthewire.org closed.

C:Users/User> ssh bandit9@bandit.labs.overthewire.org -p 2220
Enter password: EN632PlfYiZbn3PhVK3XOGSlNInNE00t
```
### Notas Adicionales
Para esta parte usamos el comando sort y uniq ambos hacen una ordenación de varios textos que coincidan con varias condiciones de búqueda.
**sort**: Ordena una salida de tanto archivos o texto por orden alfabético.
**uniq**: Muestra un archivo o texto que sea único en el documento o directorio.
### Referencias
https://overthewire.org/wargames/bandit/bandit9.html