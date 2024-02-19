# Level 11
## Objetivo
The password for the next level is stored in the file data.txt, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions.

La contraseña para el siguiente nivel se almacena en el archivo data.txt, donde todas las letras minúsculas (a-z) y mayúsculas (A-Z) se han rotado 13 posiciones.
### Datos de Acceso al nivel
Comandos: grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd
Usuario: bandit11
Contraseña: *JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv* 
Servidor: bandit.labs.overthewire.org
Puerto: 2220
### Solución
(Después de haber hecho lo del nivel 11)
```
bandit11@bandit:~$ ls
data.txt
bandit11@bandit:~$ cat data.txt
Gur cnffjbeq vf WIAOOSFzMjXXBC0KoSKBbJ8puQm5lIEi
bandit11@bandit:~$ cat data.txt | tr [a-zA-Z] [n-za-mN-ZA-M]
The password is JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv
bandit11@bandit:~$ exit
logout
Connection to bandit.labs.overthewire.org closed.

C:Users/User> ssh bandit12@bandit.labs.overthewire.org -p 2220
Enter password: JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv
```
### Notas Adicionales
Para este nivel usamos tr, que es un comando que permite utilizar los *wildcards* para poder modificar o reemplazar cadenas de texto.
**tr:** (Abreviación de Translate) Permite el reemplazo o eliminación de un conjunto de caracteres de la Entrada estándar
### Referencias
https://overthewire.org/wargames/bandit/bandit12.html