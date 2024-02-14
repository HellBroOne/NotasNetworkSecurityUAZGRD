# Level 7
## Objetivo
The password for the next level is stored in the file **data.txt** next to the word **millionth**

La contraseña para el siguiente nivel se almacena en el archivo **data.txt** junto a la palabra **millionth (millonésima)**
### Datos de Acceso al nivel
Comandos: man, grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd
Usuario: bandit7
Contraseña: *TESKZC0XvTetK0S9xNwm25STk5iWrBvP* (Descubierta)
Servidor: bandit.labs.overthewire.org
Puerto: 2220
### Solución
(Después de haber hecho lo del nivel 7)
```
bandit7@bandit:~$ ls
data.txt
bandit7@bandit:~$ wc data.txt
  98567  197133 4184396 data.txt
bandit7@bandit:~$ grep millonth data.txt
bandit7@bandit:~$ grep millionth data.txt
millionth       TESKZC0XvTetK0S9xNwm25STk5iWrBvP
bandit7@bandit:~$ cat data.txt | grep millionth
millionth       TESKZC0XvTetK0S9xNwm25STk5iWrBvP
bandit7@bandit:~$ echo "me equivoque en la palabra millionth xd"
me equivoque en la palabra millionth xd
bandit7@bandit:~$ exit
logout
Connection to bandit.labs.overthewire.org closed.

C:Users/User> ssh bandit8@bandit.labs.overthewire.org -p 2220
Enter password: TESKZC0XvTetK0S9xNwm25STk5iWrBvP
```
### Notas Adicionales
Para este nivel usamos comandos que procesan textos, como el wc y grep, para poder obtener cadenas en archivos de texto. 
**wc**: siglas de Word Count que significa contar palabras, muestra la cantidad de palabras de un archivo txt, así como los saltos de línea y los bytes del código ASCII.
**grep**: busca un patrón o una cadena de caracteres en un archivo de texto.
### Referencias
https://overthewire.org/wargames/bandit/bandit8.html