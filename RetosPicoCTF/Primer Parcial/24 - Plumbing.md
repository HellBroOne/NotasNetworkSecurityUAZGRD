## Descripción
Sometimes you need to handle process data outside of a file. Can you find a way to keep the output from this program and search for the flag? Connect to `jupiter.challenges.picoctf.org 7480`.

A veces es necesario manejar datos de proceso fuera de un archivo. ¿Puedes encontrar una manera de conservar el resultado de este programa y buscar la bandera? Conéctese a `jupiter.challenges.picoctf.org 7480`.
### Pistas
1. Remember the flag format is picoCTF{XXXX}
2. What's a pipe? No not that kind of pipe... This [kind](http://www.linfo.org/pipes.html)
### Solución
```

hellbroone-picoctf@webshell:~$ nc jupiter.challenges.picoctf.org 7480 | grep 'picoCTF{'
picoCTF{digital_plumb3r_06e9d954}
^C
hellbroone-picoctf@webshell:~$ exit
logout

Webshell session has ended.
```
### Notas Adicionales
Aquí usamos las denominadas "*pipes*" de Linux, la idea de esto es que una pipe es una "concatenación" de comandos, es para que la salida de un comando sea pasada a otra y que esta se procese al nuevo comando, generalmente se definen como: 
*[comando1] | [comando2] | ... etc.*
### Referencias
https://play.picoctf.org/practice/challenge/48