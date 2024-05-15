# Level 9
## Objetivo
The password for the next level is stored in the file **data.txt** in one of the few human-readable strings, preceded by several ‘=’ characters.

La contraseña para el siguiente nivel se almacena en el archivo **data.txt** en una de las pocas cadenas legibles por humanos, precedida por varios caracteres "=".
### Datos de Acceso al nivel
Comandos: grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd
Usuario: bandit9
Contraseña: *G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s* 
Servidor: bandit.labs.overthewire.org
Puerto: 2220
### Solución
(Después de haber hecho lo del nivel 9)
```
bandit9@bandit:~$ ls
data.txt
bandit9@bandit:~$ wc data.txt
   67   424 19379 data.txt
bandit9@bandit:~$ file data.txt
data.txt: data
bandit9@bandit:~$ strings data.txt | grep ==
x]T========== theG)"
========== passwordk^
========== is
========== G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s
bandit9@bandit:~$ exit
logout
Connection to bandit.labs.overthewire.org closed.

C:Users/User> ssh bandit10@bandit.labs.overthewire.org -p 2220
Enter password: G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s
```
### Notas Adicionales
Para este nivel usamos el comando strings, dicho comando lo combinamos mediante las barras para mostrar grep en los datos.
- **strings**: Este comando nos permite ver los caracteres legibles para humanos dentro de cualquier archivo.
### Referencias
https://overthewire.org/wargames/bandit/bandit10.html